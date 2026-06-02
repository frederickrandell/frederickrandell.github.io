# Codebase diagram

High-level structure of **frederickrandell.github.io** (GitHub Pages portfolio site).

```mermaid
flowchart TB
    subgraph config["Configuration"]
        config_yml["_config.yml\n(Jekyll: minimal theme)"]
    end

    subgraph pages["Pages"]
        index["index.html\nMain portfolio (single-page)"]
        project["project.html\nProject / landing page"]
        index_bak["index_bak.html\nBackup variant"]
        index_bs["index-bootstrap.html\nBootstrap variant"]
    end

    subgraph index_sections["index.html sections"]
        home["Home (intro, skills, socials)"]
        resume["Resume / Experience"]
        ux1["01. IA, Wireframes & Prototyping"]
        ux2["02. User Research & Testing"]
        ux3["03. Visual"]
    end

    subgraph assets["Assets (images/)"]
        img_home["fred-slice4.webp\nwireframe_with_annotations.webp"]
        img_resume["work-foxtel.webp"]
        img_ux["frame_ux_*.webp\nframe_res_*.webp\nframe_vis_*.webp\nvinyl_promo_cover.webp"]
        img_project["fred-head.jpg"]
    end

    subgraph external["External"]
        fa["Font Awesome 4.7"]
        bs5["Bootstrap 5.2.3"]
        bs_icons["Bootstrap Icons"]
    end

    config_yml -.-> index
    index --> home
    index --> resume
    index --> ux1
    index --> ux2
    index --> ux3
    index --> img_home
    index --> img_resume
    index --> img_ux
    index --> fa

    project --> index
    project --> img_project
    project --> bs5
    project --> bs_icons

    index_bak --> project
    index_bs --> bs5
    index_bs --> bs_icons
```

## File roles

| File | Role |
|------|------|
| **index.html** | Main live portfolio: custom CSS grid, single scroll page (home → resume → UX 01 → UX 02 → Visual). Uses Font Awesome. |
| **project.html** | Separate Bootstrap page with navbar and parallax hero; links back to index.html. |
| **index_bak.html** | Backup/alternate version (Bootstrap); links to project.html. |
| **index-bootstrap.html** | Bootstrap-based variant of the main portfolio content. |
| **_config.yml** | Jekyll site config (title, description, minimal theme). |
| **README.md** | Repo title only. |

## Dependencies

- **index.html**: Font Awesome (CDN).
- **project.html**, **index_bak.html**, **index-bootstrap.html**: Bootstrap 5.2.3 + Bootstrap Icons (CDN).

## Asset references

- **index.html**: `images/fred-slice4.webp`, `wireframe_with_annotations.webp`, `work-foxtel.webp`, plus multiple `frame_ux_*`, `frame_res_*`, `frame_vis_*` and `vinyl_promo_cover.webp`.
- **project.html**: `images/fred-head.jpg`.
