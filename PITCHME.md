## Some title for the presentation

<br>

#### Connor Sheehan
#### github.com/cgsheeh
#### csheehan@mozilla.com
#### IRC: sheehan

---

### Topics

- RelEng Services
- Ship-It v2!
- My work
- Wrap-Up and Thanks

---

### RelEng Services

- Move all RelEng services to one repo              |
- Define all APIs with Swagger/OpenAPI              |
- Provide a single front-end (a la TaskCluster)     |
- Build all services with Nix/Docker                |

+++

### Why One Repository?

- Service discoverability                                   |
- Re-use common components (CLI tools, Flask plugins etc)   |
- Quick overview of how/where/what is running               |

+++

### Why Swagger/OpenAPI?
<table>
<tr>
<td>
![Swagger](assets/swagger.png)
</td>

<td>
- Use *Connexion* library
- Auto-generate SwaggerUI
- Auto-generate client libraries in multiple languages
- API specifications in YAML
</td>
</tr>
</table>

---

### Ship-It v2

- Re-design of Ship-It v1
- Internal tool for starting the release process
- 
