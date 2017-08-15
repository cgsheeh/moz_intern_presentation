# Some title for the presentation

### Connor Sheehan
### McMaster University
### csheehan@mozilla.com
### IRC: sheehan

---

## Topics

- Release Engineering "*News*"
- RelEng Services
- Ship-It v2!
- My work
- Wrap-Up and Thanks

---

### RelEng Updates

- Big News: TaskCluster Migration
![Buildbot](assets/buildbot.png)
![TaskCluster](assets/taskcluster.png)

+++

### "Tiger Team"

![Tiger](assets/tiger.png)

---

### RelEng Services

- Move all RelEng services to one repo              |
- Define all APIs with Swagger/OpenAPI              |
- Provide a single front-end (a la TaskCluster)     |
- Build all services with Nix                       |

+++

### Why One Repository?

- Service discoverability                                   |
- Re-use common components (CLI tools, Flask plugins etc)   |
- Quick overview of how/where/what is running               |

+++

### Why Swagger/OpenAPI?

- Use *Connexion* library
- Auto-generate SwaggerUI
- Auto-generate client libraries in multiple languages
- YAML - easy to read for humans and machines

+++

### Why Nix?

- A step towards reproducible builds
- Dependencies... come again?
- Managed environments
