```mermaid
classDiagram
    UI --|> Authentication
    UI --|> API
    API --|> Backend
    Backend --|> Database
    class UI {
        React
        SPA
        Material UI
    }
    class API {
        Django REST framework
    }
    class Backend {
        Model from Django MVT
    }
    class Database {
        Userdata
    }
    class Authentication {
        Google OAauth
    }
```

## Notes

React

- Single Page Applicatoin
- Material UI

REST-API

- all/
- consult/name
- certs/?certification=cert1,cert2, cert3
- skills/?skill=skill1,skill2,skill3
- startdate/

Other notes

- Certifications and Skills from Database through API?
