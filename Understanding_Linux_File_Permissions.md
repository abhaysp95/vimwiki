# Linux Security:

From page 197 to 200

The `/etc/passwd` files contain following things:
* The login username
* The password for the user
* The numerical UID of the user account
* The numerical group ID(GID) of the user account
* The text description of the user account(called comment field)
* The location of the `HOME` directory for the user
* The default shell for the user.

Now, most Linux systems hold the user passwords in a separate file(called the `shadow` file, located at /etc/shadow). No read access allowed
In page 200

# Adding/Removing a user:

From page 200-204, use of `useradd` command and how to manipulate it

# Modifying a user

From page 204-

### User Account Modification Utilities

| **Command** | **Description**                                 |
|-------------|-------------------------------------------------|
| usermod     | Edit user account fields, as well as specifying |
|             | primary and secondary group membership          |
| passwd      | Changes the password for an existing user       |
| chpasswd    | Reads a file login name and password pairs, and |
|             | updates the passwords                           |
| chfn        | Changes the user account's comment information  |
| chage       | Changes the password's expiration date          |
| chsh        | Changes the user account's default shell        |

