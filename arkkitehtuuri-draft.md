# Application Architecture

```mermaid
flowchart
    subgraph Server: HetznerVPS
        subgraph Container: Docker
            ui[UI\n_______\nReact\nSPA\nMaterial UI]
            djangoapi[API\n_____________________\nDjango REST framework]
            backend[Backend\n____\nModel from Django MVT]
            db[Database\n______\nPostgreSQL]
            ui-->djangoapi
            djangoapi-->backend
            ui-->backend
            backend-->db
        end
    end
    backend --> oauth[OAuth API\n___________\nGoogle OAuth]
```

## Overview

**Server**

- Hetzner VPS

**Container**

- Docker container

**UI**

- React Application
  - Single Page Application design style
  - Material UI: React Component library for styling web content

**API**

- API: Django REST framework

**Backend**

- Django: Python web framework
  - Implement Model from Django MVT

**Database**

- PostgreSQL

**Authentication (OAuth)**

- Google OAuth: OAuth 2.0 protocol

## Initial proposal for API-routes

- all/
- consult/name
- certs/?certification=cert1,cert2, cert3
- skills/?skill=skill1,skill2,skill3
- startdate/

Other notes

- Certifications and Skills from Database through API?
