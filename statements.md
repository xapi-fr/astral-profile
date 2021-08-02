# Profil Astral : Statements

---

- [Règles communes](#rules)
- [Achèvement d'une simulation](#completion)
- [Enregistrement des compétences](#competencies)
- [Annulation](#voiding)


<a name="rules"></a>
## Règles communes

- La propriété `object.definition.name` DOIT être précisée. Elle indique le nom de la simulation.
- Le `type` des activités DOIT être précisé et fixé à `http://adlnet.gov/expapi/activities/simulation`.
- L'extension d'activité `remedial` DOIT être présente.
- La propriété `result.completion` DOIT être présente et avoir pour valeur `true`.
- La propriété `context.contextActivities.parent` DOIT mentionner le degré concerné.
- La propriété `context.contextActivities.grouping` DOIT mentionner la formation concernée (registration).
- La propriété `context.contextActivities.category` DOIT mentionner le niveau de granularité en utilisant comme ID : `http://vocab.xapi.fr/categories/learning-unit`.
- Le profil Astral DOIT être indiqué dans la propriété `context.contextActivities.category`. 
- La propriété `context.platform` DOIT être précisée et avoir pour valeur `ASTRAL`.
- La propriété `context.instructor` DOIT être présente et préciser l'instructeur concerné.


<a name="completion"></a>
## Achèvement d'une simulation

- L'extension de résultat `go-ground` DOIT être présente.

``` json
{
    "actor": {
        "objectType": "Agent",
        "account": {
            "name": "f2b0adcb-a696-3c5f-aed9-ebca5b7aae91",
            "homePage": "https://astral.enac.fr"
        }
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/completed"
    },
    "object": {
        "objectType": "Activity",
        "id": "https://astral.enac.fr/xapi/activities/training-items/0e032b33-83d4-3b8a-acfc-613a63cdb70c",
        "definition": {
            "type": "http://adlnet.gov/expapi/activities/simulation",
            "name": {
                "en": "SIM1"
            },
            "extensions": {
                "http://vocab.xapi.fr/extensions/remedial": false,
            }
        }
    },
    "result": {
        "completion": true,
        "extensions": {
            "https://astral.enac.fr/xapi/vocab/extensions/go-ground": false,
        }
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "id": "https://astral.enac.fr/xapi/activities/training-modules/d539b903-cda9-34a2-8ed3-8307e7245b87",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/training-module"
                    }
                }
            ],
            "grouping": [
                {
                    "id": "https://astral.enac.fr/xapi/activities/registrations/a7594730-3c60-3168-8df1-97ab586e24c5",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/registration"
                    }
                }
            ],
            "category": [
                {
                    "id": "http://vocab.xapi.fr/categories/learning-unit",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/granularity-level"
                    }
                },
                {
                    "id": "https://astral.enac.fr/xapi/vocab/categories/profile",
                    "definition": {
                        "type": "http://adlnet.gov/expapi/activities/profile"
                    }
                }
            ]
        },
        "instructor": {
            "objectType": "Agent",
            "account": {
                "name": "b1f6a84b-de23-3e28-9f34-48344e2f20df",
                "homePage": "https://astral.enac.fr"
            }
        },
        "platform": "ASTRAL",
    },
}
```

<a name="completion"></a>
## Enregistrement des compétences

- Un statement est émis par position évaluée.
- L'extension de résultat `position` DOIT être présente.
- L'extension de résultat `assessment-items` DOIT être présente.

``` json
{
    "actor": {
        "objectType": "Agent",
        "account": {
            "name": "f2b0adcb-a696-3c5f-aed9-ebca5b7aae91",
            "homePage": "https://astral.enac.fr"
        }
    },
    "verb": {
        "id": "http://vocab.xapi.fr/verbs/was-assessed"
    },
    "object": {
        "objectType": "Activity",
        "id": "https://astral.enac.fr/xapi/activities/training-items/0e032b33-83d4-3b8a-acfc-613a63cdb70c",
        "definition": {
            "type": "http://adlnet.gov/expapi/activities/simulation",
            "name": {
                "en": "SIM1"
            },
            "extensions": {
                "http://vocab.xapi.fr/extensions/remedial": false,
            }
        }
    },
    "result": {
        "completion": true,
        "extensions": {
            "https://astral.enac.fr/xapi/vocab/extensions/position": "sol",
            "http://vocab.xapi.fr/extensions/assessment-items": [
                {
                    "id": "https://astral.enac.fr/xapi/activities/competencies/69a29369-0946-3777-94d1-8db8762f4da0",
                    "value": 1
                },
                {
                    "id": "https://astral.enac.fr/xapi/activities/competencies/ef73fc17-db93-3a96-b10f-34ebea6cc140",
                    "value": 2
                }
            ]
        }
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "id": "https://astral.enac.fr/xapi/activities/training-modules/d539b903-cda9-34a2-8ed3-8307e7245b87",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/training-module"
                    }
                }
            ],
            "grouping": [
                {
                    "id": "https://astral.enac.fr/xapi/activities/registrations/a7594730-3c60-3168-8df1-97ab586e24c5",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/registration"
                    }
                }
            ],
            "category": [
                {
                    "id": "http://vocab.xapi.fr/categories/learning-unit",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/granularity-level"
                    }
                },
                {
                    "id": "https://astral.enac.fr/xapi/vocab/categories/profile",
                    "definition": {
                        "type": "http://adlnet.gov/expapi/activities/profile"
                    }
                }
            ]
        },
        "instructor": {
            "objectType": "Agent",
            "account": {
                "name": "b1f6a84b-de23-3e28-9f34-48344e2f20df",
                "homePage": "https://astral.enac.fr"
            }
        },
        "platform": "ASTRAL",
    },
}
```

<a name="voiding"></a>
## Annulation

L'annulation de Statements peut se produire en cas de réouverture d'un dossier élève. Dans ce cas, tous les Statements concernés par le dossier sont annulés.

```json
{
    "actor": {
        "objectType": "Agent",
        "account": {
            "name": "e1002439-9407-3cf3-b8c3-0828c9c14435",
            "homePage": "https://polaris.enac.fr"
        }
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/voided"
    },
    "object": {
        "objectType": "StatementRef",
        "id": "e08b435b-846b-3f03-a95f-d5792b0176ef"
    },
}
```


