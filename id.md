# Profil Astral : Identification

---

- [Agents](#agents)
- [Activités](#activities)
- [Profil](#profile)


<a name="agents"></a>
## Agents

L'identification des Agents repose sur le format `account`. 

L'IRI de la plateforme (`homePage`) est stable, y compris si la plateforme change de nom de domaine. 

Le nom de l'utilisateur (`name`) est anonymisée : l'identifiant réel est remplacé par un UUID. La correspondance entre identifiant réel et UUID est gérée au sein de la plateforme Polaris. 

``` json
"actor": {
    "objectType": "Agent",
    "account": {
        "homePage": "https://astral.enac.fr",
        "name": "8be985de-9d4f-331a-8f06-fd4bab2030f7"
    }
}
```

<a name="activities"></a>
## Activités

- Les séances de simuation sont identifiées selon le schéma `https://astral.enac.fr/xapi/activities/training-items/xxx`, où `xxx` est l'UUID de la simulation.

- Les degrés sont identifiées selon le schéma `https://astral.enac.fr/xapi/activities/training-modules/xxx`, où `xxx` est l'UUID du degré.

- Les formations (registrations) sont identifiées selon le schéma `https://astral.enac.fr/xapi/activities/registrations/xxx`, où `xxx` est l'UUID de la formation.

- Les compétences sont identifiés selon le schema `https://astral.enac.fr/xapi/activities/competencies/xxx`, où `xxx` est l'UUID de la compétence.


<a name="profile"></a>
## Profil Astral

Le profil Astral est identifié par `https://astral.enac.fr/xapi/vocab/categories/profile`.



