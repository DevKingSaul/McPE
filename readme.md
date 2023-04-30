# Current Protocol Encryption
### Shared Secret is generated, and encrypted
## Login Start (Client > Server)
| Username | The Username of player logging in |
| :---: | :--- |

## Encryption Request (Server > Client)
| Server ID | Empty |
| :---: | :--- |
| Public Key | Server's RSA Public Key |
| Verify Token | 4 random bytes, must be matched by client |

## Encryption Response (Client > Server)
| Shared Secret | 16 random bytes encrypted with Server's RSA Public Key, used for encryption |
| :---: | :--- |
| Verify Token | Verify token sent by server encrypted with the Server's RSA Public Key |
#### Encryption is Enabled

## Set Compression (Server > Client)
| Threshold | The Minimum Byte Size for Compression |
| :---: | :--- |

## Login Success (Server > Client)
| UUID | The Unique Identifier for the player logging in |
| :---: | :--- |
| Username | The Username of player logging in |



# Proposed Protocol Encryption (Compatible)
### Shared Secret is calculated from keypairs
## Login Start (Client > Server)
| Username | The Username of player logging in |
| :---: | :--- |

## Login Plugin Request (Server > Client)
| Message ID | Random Variable Integer |
| :---: | :--- |
| Channel | minecraft:enhanced_encrypt |
| Data | empty |

## Login Plugin Response (Client > Server)
| Message ID | Random Variable Integer |
| :---: | :--- |
| Message ID | Same Message ID as previous packet |
| Successful | Yes |
| Data | empty |

## Encryption Request (Server > Client)
| Server ID | Empty |
| :---: | :--- |
| Public Key | Server's ECDH Public Key |
| Verify Token | 32 random bytes, must be matched by client |

## Encryption Response (Client > Server)
| Shared Secret | Client's ECDH Public Key |
| :---: | :--- |
| Verify Token | Verify token sent by server encrypted with the shared secret |
#### Encryption is Enabled

## Set Compression (Server > Client)
| Threshold | The Minimum Byte Size for Compression |
| :---: | :--- |

## Login Success (Server > Client)
| UUID | The Unique Identifier for the player logging in |
| :---: | :--- |
| Username | The Username of player logging in |
