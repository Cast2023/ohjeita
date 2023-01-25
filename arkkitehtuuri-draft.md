# Application Architecture

## Overview

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

## Notes

React

- Single Page Application
- Material UI

REST-API
An initial proposal for API-routes:

- all/
- consult/name
- certs/?certification=cert1,cert2, cert3
- skills/?skill=skill1,skill2,skill3
- startdate/

Other notes

- Certifications and Skills from Database through API?
