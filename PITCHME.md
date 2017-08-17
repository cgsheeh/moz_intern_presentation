## Building Modern Microservices

<br>

#### Connor Sheehan
#### Release Engineering Intern
#### github.com/cgsheeh
#### IRC: sheehan

---

### Topics

- RelEng Services
- Ship-It v2
- My work
- Wrap-Up and Thanks

---

### RelEng Services

- Move all RelEng services to one repo              |
- Define all HTTP APIs with Swagger/OpenAPI         |
- Provide a unified front-end                       |

---

### Swagger/OpenAPI
![Swagger](assets/swagger.png)

- Use Connexion library                                     |
- Auto-generate SwaggerUI                                   |
- Client library generation                                 |
- API specifications in YAML                                |

---

```yaml
swagger: "2.0"
info:
  version: "1.0.0"
  title: "RelEng Notification Policy"
  description: |
    Releng Notification Policy service manages the 
    sending and acknowledging of RelEng notification
    messages based on notification policies.
  contact:
    name: Mozilla Release Engineering
    url: 'https://wiki.mozilla.org/ReleaseEngineering'
    email: release@mozilla.com
  license:
    name: Mozilla Public License Version 2.0
    url: 'https://www.mozilla.org/en-US/MPL/2.0/'

consumes:
  - application/json
produces:
  - application/json

paths:
  '/message/{uid}':
      put:
          summary: Add a new notification message to the service.
          operationId: "releng_notification_policy.api.put_message"
          parameters:
            - name: uid
              in: path
              type: string
              description: Tracking UID for message.
              required: true
    
            - name: body
              in: body
              required: true
              description: Notification message to add to the service.
              schema:
                $ref: '#/definitions/Message'
    
          responses:
            200:
              description: Notification policy created.
            409:
              description: Message or policy with the specified UID already exists
              schema:
                $ref: '#/definitions/Problem'
            400:
              description: Could not create the notification policy
              schema:
                $ref: '#/definitions/Problem'
```

@[1-19](Specify app metadata)
@[21-26](Define URL endpoints and bind to Python views)
@[27-39](Define required input parameters)
@[40-50](Define response codes, their format and context)

---

---?video=assets/swagger_ui.mp4

---

### Ship-It v2

![Ship-it](assets/shipit.png)

- Cross-team tool (RelEng, RelMan, QE, etc)     |
- Co-ordinate releases                          |
- Monitor automation handoffs                   |


---

### Manual Sign-offs

![Pipeline](assets/pipeline.jpg)

- Model release as a "pipeline"                                 |
- Output of one pipeline is input of another                    |
- Humans sign-off between pipelines                             |

---

### Escalating Notifications

- Two notification micro-services ("NagBot")                                |
    - Identity: preferences (low, med, high)                                |
    - Policy: policies (1pm to 5pm, every 15 mins)                          |
- Compose policies to "escalate" notifications                              |

---

### Elm UI Component

<img src="assets/elm.png" width="25%" height=25%>

- Compiles to JS, statically typed, functional      |
- Great compiler errors - refactor confidently      |
- Virtual DOM (ReactJS)                             |


---

![NagBotUI](assets/nagbotui.png)

---

---?image=assets/releng_team.jpg&size=contain

---

### Thank you!

- Mentors (Rail Aliiev, Rok Garbas)
- Managers (Chris Cooper, Chris AtLee)
- Release Engineering Team
- Toronto office folk
- Interns!
