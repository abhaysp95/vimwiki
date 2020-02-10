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

# Adding a new user:

From page 200
