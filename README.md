 # BeSocial

  Prototype of a small social network built as a console application in C++. Users can register, log in, write posts and read posts
  from other users. There's also an anonymous mode that only allows reading.

  All data is stored in plain text files inside the `data/` folder — one file per user (`user_<name>.fcp`) plus a shared `Post.txt` for
   posts.

  Originally developed in Dev-C++ on Windows.

  ## Features

  - Account creation with username, password, date of birth and email
  - Login and authentication against the per-user files
  - Creating posts (timestamped and tied to the logged-in user)
  - Browsing posts from all users
  - Anonymous mode (read-only)
  - Optional statistics menu when launched with `--stats`

  ## Build

  The project ships with a Dev-C++ Makefile (`Makefile.win`) that points at the MinGW paths from a Dev-C++ install. To build with a
  regular `g++`:

  ```bash
  g++ -o RedeSocial main.cpp utilizadores.cpp post.cpp

  Or, on Windows with the original toolchain:

  mingw32-make -f Makefile.win

  Run

  ./RedeSocial
  ./RedeSocial --stats   # enables the extra statistics option in the main menu
```
  Project layout

  .
  ├── main.cpp              # menus and program entry point
  ├── utilizadores.cpp/.h   # account creation and login
  ├── post.cpp/.h           # creating and listing posts
  ├── Makefile.win          # Dev-C++ generated makefile
  ├── RedeSocial.dev        # Dev-C++ project file
  └── data/
      ├── Post.txt          # all posts
      └── user_*.fcp        # one file per registered user

  Notes

  - Source code, menus and comments are in Portuguese, kept as originally submitted.
  - Passwords are stored in plain text in the user files. This is a learning project, not something to deploy.
  - Console clearing relies on system("clear||cls") so it works on both Windows and Unix-like terminals.
  - The data/ folder already contains a few sample users and posts — wipe it if you want to start fresh.

  Context

  University project for an introductory programming course.
