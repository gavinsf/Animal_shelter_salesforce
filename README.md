# Animal Shelter Salesforce
- Designed independently in schema.txt
- Built using Claude LLM with Salesforce CLI


## Objects
### Animal
| Field | Type | Required |
|---|---|---|
| Name | Text | Yes |
| Species | Picklist (Dog, Cat, Rabbit) | Yes |
| Breed | Text | Yes |
| Intake_status | Picklist (Adopted, Recovery, Available, New, Reclaimed) | Yes |
| Intake_date | Date | Yes |

### Medical_Record
| Field | Type | Required |
|---|---|---|
| Animal | Master-Detail | Yes |
| Visit_date | Date | Yes |
| Procedure | Text | Yes |
| Vet | Lookup | Yes |
| Additional_info | Long Text | No |

### Vet
| Field | Type | Required |
|---|---|---|
| Name | Text | Yes |
| Location | Text (Long) | Yes |
| Phone | Phone | Yes |
| Email | Email | Yes |
| Website | URL | No |

### Adoption
| Field | Type | Required |
|---|---|---|
| Adopter | Lookup | Yes |
| Animal | Lookup | Yes |
| Adoption_date | Date | Yes |
| Fee | Currency | No |

### Person
| Field | Type | Required |
|---|---|---|
| Name | Text | Yes |
| Phone | Phone | Yes |
| Email | Email | Yes |

### Adopter
| Field | Type | Required |
|---|---|---|
| Person | Lookup | Yes |
| Address | Text (Long) | Yes |
| Age | Number | Yes |
| Home_checked | Boolean | No |

### Home_Information
| Field | Type | Required |
|---|---|---|
| Adopter | Master-Detail | Yes |
| Type | Picklist (house, apartment, condo, acreage) | Yes |
| Renting | Boolean | Yes |
| Details | Long Text | No |
| Has_yard | Boolean | No |

### Pet_Experience
| Field | Type | Required |
|---|---|---|
| Adopter | Master-Detail | Yes |
| Current_pets | Long Text | No |
| Current_pets_spayed | Boolean | No |
| Current_pets_vaccinated | Boolean | No |

## Donation
| Field | Type | Required |
|---|---|---|
| Person | Lookup | Yes |
| Amount | Currency | Yes |
| Date | Date | Yes |
