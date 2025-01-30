# Libft


- [1 About](#1-about)
- [2 Documentation](#2-documentation)
  - [2.1 libc functions](#21-libc-functions)
  - [2.2 Additional functions](#22-additional-functions)
  - [2.3 List functions](#23-list-functions)

# 1 About

This is my 42 libft library. Here I’ll create **C** utility functions to
use in future projects.

# 2 Documentation

## 2.1 libc functions

### ft_isalpha

- **Description:** Checks if a character is alphabetic (upper or lower)
- **Arguments:**
  - `c (int)`: An unsigned char to check
- **Return:** None zero if true (1024), zero if false
- **Requires:** None

### ft_isdigit

- **Description:** Checks if a character is a digit (0 to 9)
- **Arguments:**
  - `c (int)`: An unsigned char to check
- **Return:** None zero if true (2048), zero if false
- **Requires:** None

### ft_isalnum

- **Description:** Checks if a character is a digit or alphabetic (upper
  or lower)
- **Arguments:**
  - `c (int)`: An unsigned char to check
- **Return:** None zero if true (8), zero if false
- **Requires:** `libft::(ft_isalpha, ft_isdigit)`

### ft_isascii

- **Description:** Checks if a character is a 7-bit unsigned char ASCII
  character set (0 to 127)
- **Arguments:**
  - `c (int)`: An unsigned char to check
- **Return:** None zero if true (1), zero if false
- **Requires:** None

### ft_isprint

- **Description:** Checks if a character is printable (32 to 126)
- **Arguments:**
  - `c (int)`: An unsigned char to check
- **Return:** None zero if true (16384), zero if false
- **Requires:** None

### ft_strlen

- **Description:** Calculate the length of a string, excluding ‘\0’
- **Arguments:**
  - `s (const char *)`: String to calculate the length
- **Return:** (`size_t`). Length of the string
- **Requires:** None (`const stddef::size_t`)

### ft_memset

- **Description:** Fills the first `n` bytes of the pointer `s` with the
  constant byte `c`. The `n` bytes of the memory need to be accessible
- **Arguments:**
  - `s (void *)`: Pointer to memory
  - `c (int)`: Constant byte
  - `n (size_t)`: Number of bytes to fill
- **Return:** (`Void`) Original pointer `s` filled
- **Requires:** None (`const stddef::size_t`)

### ft_bzero

- **Description:** Fills the first `n` bytes of the pointer `s` with the
  character ‘\0’
- **Arguments:**
  - `s (void *)`: Pointer to memory
  - `n (size_t)`: Number of bytes to fill
- **Return:** (`Void`). It will modify s
- **Requires:** `libft::ft_memset` (`const stddef::size_t`)

### ft_memcpy

- **Description:** Copies `n` bytes from the pointer `src` to the
  pointer `dest`. **Can** fail if memory `src` and `dest` overlap.
- **Arguments:**
  - `dest (void *)`: Pointer to memory destination
  - `src (void *)`: Pointer to memory source bytes
  - `n (size_t)`: Number of bytes to copy
- **Return:** (`Void`) It will modify `dest`
- **Requires:** None (`const stddef::size_t`)

### ft_memmove

- **Description:** Copies `n` bytes from the pointer `src` to the
  pointer `dest`. **Can’t** fail if memory `src` and `dest` overlap.
- **Arguments:**
  - `dest (void *)`: Pointer to memory destination
  - `src (void *)`: Pointer to memory source bytes
  - `n (size_t)`: Number of bytes to copy
- **Return:** (`Void`) It will modify `dest`
- **Requires:** None (`const stddef::size_t`)

### ft_strlcpy

- **Description:** Copies `size - 1` bytes from the string `src` to the
  string `dst`, and `NULL` terminate (‘\0’) the result. User needs to
  allocate at least `size` bytes of memory in `dst`
- **Arguments:**
  - `dest (void *)`: Character string destination
  - `src (void *)`: Character string source
  - `size (size_t)`: Number of characters to copy from `src + 1`
- **Return:** (`size_t`) Length of `src`. It will modify `dest`
- **Requires:** None (`const stddef::size_t`)

### ft_strlcat

- **Description:** Appends `size - strlen(dst) - 1` bytes from the
  string `src` at the end of the string `dst`, and `NULL` terminate the
  result. User needs to allocate at least `size` bytes of memory in
  `dst`
- **Arguments:**
  - `dest (void *)`: Character string destination
  - `src (void *)`: Character string source
  - `size (size_t)`: Number of characters to copy from `src + 1`
- **Return:** (`size_t`) Length of `src + dst`. If size is too short,
  returns `size + dst`
- **Requires:** `libft::ft_strlcpy` (`const libft::size_t`)

### ft_toupper

- **Description:** If `c` is lowercase, it returns the uppercase match.
  Else returns `c`
- **Arguments:**
  - `c (int)`: Character
- **Return:** (`int`) Character transformed if necessary
- **Requires:** None

### ft_tolower

- **Description:** If `c` is uppercase, it returns the lowercase match.
  Else returns `c`
- **Arguments:**
  - `c (int)`: Character
- **Return:** (`int`) Character transformed if necessary
- **Requires:** None

### ft_strchr

- **Description:** Search the first occurrence of the character `c` in
  the string `s`. The null byte is considered part of the string
- **Arguments:**
  - `s (const char *)`: String to search
  - `c (int)`: Character to find
- **Return:** (`char *`) Pointer to the match character, or `NULL` if
  not found
- **Requires:** None

### ft_strrchr

- **Description:** Search the last occurrence of the character `c` in
  the string `s`. The null byte is considered part of the string
- **Arguments:**
  - `s (const char *)`: String to search
  - `c (int)`: Character to find
- **Return:** (`char *`) Pointer to the match character, or `NULL` if
  not found
- **Requires:** None

### ft_strncmp

- **Description:** Compares the first `n` characters from `s1` and `s2`
  strings
- **Arguments:**
  - `s1 (const char *)`: String 1
  - `s2 (const char *)`: String 2
  - `n (size_t)`: Number of characters to compare
- **Return:** (`int`) 0 means a match, else a difference, can be
  positive or negative
- **Requires:** None (`const libft::size_t`)

### ft_memchr

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_memcmp

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_strnstr

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_atoi

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_calloc

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:** `stdlib::malloc`

### ft_strdup

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:** `stdlib::malloc`

## 2.2 Additional functions

### ft_substr

- **Description:** Creates new substring from string `s`, starting from
  the idx `start` and max length `len`
- **Arguments:**
  - `s (char*)`: Starting string
  - `start (int)`: Starting index
  - `len (int)`: Max substring length
- **Return:** (char) Memory allocated substring, NULL if memory
  allocation fails
- **Requires:** `stdlib::malloc` (`const limits::size_t`)

### ft_strjoin

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_strtrim

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_split

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_itoa

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_strmapi

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_striteri

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_putchar_fd

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_putstr_fd

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_putendl_fd

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_putnbr_fd

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

## 2.3 List functions

Check type `t_list` in [libft.h](libft.h).

### ft_lstnew

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_lstadd_front

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_lstsize

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_lstlast

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_lstadd_back

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_lstdelone

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_lstclear

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_lstiter

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**

### ft_lstmap

- **Description:**
- **Arguments:**
- **Return:**
- **Requires:**
