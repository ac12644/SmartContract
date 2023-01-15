# MedicalRecord Contract

This contract represents a medical records system that allows authorized users to access and manage medical records.

## Functions

### authorizeUser

This function grants authorization to a user to access records.

##### Inputs:

- user: The address of the user to be authorized.

##### Outputs:

None.

### removeAuthorization

This function revokes authorization from a user to access records.

##### Inputs:

- user: The address of the user to have their authorization revoked.

##### Outputs:

None.

#### setUserRole

This function sets the role of a user.

##### Inputs:

- user: The address of the user to have their role set.
- role: The role to be assigned to the user.

##### Outputs:

None.

#### getRecord

This function retrieves a medical record.

##### Inputs:

- key: The key of the record to be retrieved.

##### Outputs:

- data: The data of the retrieved record.

#### setRecord

This function adds or updates a medical record.

##### Inputs:

- key: The key of the record to be added or updated.
- data: The data of the record.
- expirationDate: The expiration date of the record.
- minRole: The minimum role required to access the record.
- authorizedUsers: An array of addresses of users who are authorized to access the record.

##### Outputs:

None.

#### deleteRecord

This function deletes a medical record.

##### Inputs:

- key: The key of the record to be deleted.

##### Outputs:

None.

#### getOwner

This function retrieves the owner of the contract.

##### Inputs:

None.

##### Outputs:

## Variables

#### records

This is a mapping of medical records, where the key is a bytes32 value and the value is a Record struct.

#### accessRestrictions

This is a mapping of access restrictions for each record, where the key is a bytes32 value and the value is a Restrictions struct.

### authorizedUsers

This is a mapping that stores the addresses of users who are authorized to access records.

### userRoles

This is a mapping that stores the role of each user.

## Structs

### Record

This struct stores the data and timestamp for a medical record.

##### Fields:

- data: The data of the record.
- timestamp: The timestamp of when the record was added or last updated.

### Restrictions

This struct stores the access restrictions for a medical record.

##### Fields:

- authorizedUsers: A mapping of addresses of users who are authorized to access the record.
- minRole: The minimum role required to access the record.
- expirationDate: The expiration date of the record.

## Modifiers

### onlyOwner

This modifier allows only the owner of the contract to call a function.

### onlyAuthorized

This modifier allows only authorized users to call a function.

- owner: The address of the owner of the contract.

## Enums

### Roles

This enum defines the possible roles that a user can have.

##### Values:

- Patient: A patient role.
- Doctor: A doctor role.
- Administrator: An administrator role.

## Examples

Here are some examples of how to use the contract's functions:

```solidity
// Grant authorization to a user
medicalRecord.authorizeUser(<user address>)

// Set the role of a user
medicalRecord.setUserRole(<user address>, Roles.Doctor)

// Add a medical record
medicalRecord.setRecord(<key>, <data>, <expiration date>, <min role>, [<authorized user address>, ...])

// Retrieve a medical record
medicalRecord.getRecord(<key>)

// Delete a medical record
medicalRecord.deleteRecord(<key>)

// Get the owner of the contract
medicalRecord.getOwner()

```
