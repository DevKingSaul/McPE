# Current Protocol Encryption
## Login Start (Client > Server)
| Username | The Username of player logging in |
| :---: | :--- |

## Encryption Request (Server > Client)
| Server ID | Empty |
| :---: | :--- |
| Public Key | Server's RSA Public Key |
| Verify Token | 4 random bytes, must be matched by client |

## Encryption Response (Client > Server)
| Server ID | Empty |
| :---: | :--- |
| Shared Secret | 16 random bytes encrypted with Server's RSA Public Key, used for encryption |
| Verify Token | verify token sent by server encrypted with the Server's RSA Public Key |
### Encryption is Enabled

## Set Compression (Server > Client)
| Threshold | The Minimum Byte Size for Compression |
| :---: | :--- |

## Login Success (Server > Client)
| UUID | The Unique Identifier for the player logging in |
| :---: | :--- |
| Username | The Username of player logging in |
