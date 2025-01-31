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

`int ft_isalpha(int c)`

- **Description:** Checks if a character is alphabetic (upper or lower)
- **Arguments:**
  - `c (int)`: An unsigned char to check
- **Return:** None zero if true (1024), zero if false
- **Requires:** None

### ft_isdigit

`int ft_isdigit(int c)`

- **Description:** Checks if a character is a digit (0 to 9)
- **Arguments:**
  - `c (int)`: An unsigned char to check
- **Return:** None zero if true (2048), zero if false
- **Requires:** None

### ft_isalnum

`int ft_isalnum(int c)`

- **Description:** Checks if a character is a digit or alphabetic (upper
  or lower)
- **Arguments:**
  - `c (int)`: An unsigned char to check
- **Return:** None zero if true (8), zero if false
- **Requires:** `libft::(ft_isalpha, ft_isdigit)`

### ft_isascii

`int ft_isascii(int c)`

- **Description:** Checks if a character is a 7-bit unsigned char ASCII
  character set (0 to 127)
- **Arguments:**
  - `c (int)`: An unsigned char to check
- **Return:** None zero if true (1), zero if false
- **Requires:** None

### ft_isprint

`int ft_isprint(int c)`

- **Description:** Checks if a character is printable (32 to 126)
- **Arguments:**
  - `c (int)`: An unsigned char to check
- **Return:** None zero if true (16384), zero if false
- **Requires:** None

### ft_strlen

`size_t ft_strlen(const char *s)`

- **Description:** Calculate the length of a string, excluding ‘\0’
- **Arguments:**
  - `s (const char *)`: String to calculate the length
- **Return:** (`size_t`). Length of the string
- **Requires:** None (`const stddef::size_t`)

### ft_memset

`void *ft_memset(void *s, int c, size_t n)`

- **Description:** Fills the first `n` bytes of the pointer `s` with the
  constant byte `c`. The `n` bytes of the memory need to be accessible
- **Arguments:**
  - `s (void *)`: Pointer to memory
  - `c (int)`: Constant byte
  - `n (size_t)`: Number of bytes to fill
- **Return:** (`Void`) Original pointer `s` filled
- **Requires:** None (`const stddef::size_t`)

### ft_bzero

`void ft_bzero(void *s, size_t n)`

- **Description:** Fills the first `n` bytes of the pointer `s` with the
  character ‘\0’
- **Arguments:**
  - `s (void *)`: Pointer to memory
  - `n (size_t)`: Number of bytes to fill
- **Return:** (`Void`). It will modify s
- **Requires:** `libft::ft_memset` (`const stddef::size_t`)

### ft_memcpy

`void *ft_memcpy(void *dest, const void *src, size_t n)`

- **Description:** Copies `n` bytes from the pointer `src` to the
  pointer `dest`. **Can** fail if memory `src` and `dest` overlap.
- **Arguments:**
  - `dest (void *)`: Pointer to memory destination
  - `src (void *)`: Pointer to memory source bytes
  - `n (size_t)`: Number of bytes to copy
- **Return:** (`Void`) It will modify `dest`
- **Requires:** None (`const stddef::size_t`)

### ft_memmove

`void *ft_memmove(void *dest, const void *src, size_t n)`

- **Description:** Copies `n` bytes from the pointer `src` to the
  pointer `dest`. **Can’t** fail if memory `src` and `dest` overlap.
- **Arguments:**
  - `dest (void *)`: Pointer to memory destination
  - `src (void *)`: Pointer to memory source bytes
  - `n (size_t)`: Number of bytes to copy
- **Return:** (`Void`) It will modify `dest`
- **Requires:** None (`const stddef::size_t`)

### ft_strlcpy

`size_t ft_strlcpy(char *dst, const char *src, size_t size)`

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

`size_t ft_strlcat(char *dst, const char *src, size_t size)`

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

`int ft_toupper(int c)`

- **Description:** If `c` is lowercase, it returns the uppercase match.
  Else returns `c`
- **Arguments:**
  - `c (int)`: Character
- **Return:** (`int`) Character transformed if necessary
- **Requires:** None

### ft_tolower

`int ft_tolower(int c)`

- **Description:** If `c` is uppercase, it returns the lowercase match.
  Else returns `c`
- **Arguments:**
  - `c (int)`: Character
- **Return:** (`int`) Character transformed if necessary
- **Requires:** None

### ft_strchr

`char *ft_strchr(const char *s, int c)`

- **Description:** Search the first occurrence of the character `c` in
  the string `s`. The null byte is considered part of the string
- **Arguments:**
  - `s (const char *)`: String to search
  - `c (int)`: Character to find
- **Return:** (`char *`) Pointer to the match character, or `NULL` if
  not found
- **Requires:** None

### ft_strrchr

`char *ft_strrchr(const char *s, int c)`

- **Description:** Search the last occurrence of the character `c` in
  the string `s`. The null byte is considered part of the string
- **Arguments:**
  - `s (const char *)`: String to search
  - `c (int)`: Character to find
- **Return:** (`char *`) Pointer to the matching character, or `NULL` if
  not found
- **Requires:** None

### ft_strncmp

`int ft_strncmp(const char *s1, const char *s2, size_t n)`

- **Description:** Compares the first `n` characters from `s1` and `s2`
  strings
- **Arguments:**
  - `s1 (const char *)`: String 1
  - `s2 (const char *)`: String 2
  - `n (size_t)`: Number of characters to compare
- **Return:** (`int`) 0 means a match, else a difference, can be
  positive or negative
- **Requires:** None (`const stddef::size_t`)

### ft_memchr

`void *ft_memchr(const void *s, int c, size_t n)`

- **Description:** Scans the initial `n` bytes of the pointer `s`,
  looking for the byte `c`
- **Arguments:**
  - `s (const char *)`: Pointer to search
  - `c (int)`: Byte to find
  - `n (size_t)`: Number of bytes to scan
- **Return:** (`void *`) Pointer to the matching byte, or `NULL` if not
  found
- **Requires:** None (`const stddef::size_t`)

### ft_memcmp

`int ft_memcmp(const void *s1, const void *s2, size_t n)`

- **Description:** Compares the first `n` bytes between `s1` and `s2`
  (interpreted as unsigned char)
- **Arguments:**
  - `s1 (const char *)`: Pointer 1
  - `s2 (const char *)`: Pointer 2
  - `n (size_t)`: Number of bytes to compare
- **Return:** (`int`) 0 means a match, else a difference, can be
  positive or negative
- **Requires:** None (`const stddef::size_t`)

### ft_strnstr

`char *ft_strnstr(const char *big, const char *little, size_t len)`

- **Description:** Scans the first `len` characters of string `big` for
  the string `little`
- **Arguments:**
  - `big (const char *)`: String to search to
  - `little (const char *)`: String to find
  - `len (size_t)`: Number of characters to search
- **Return:** (`char *`) If match, a pointer to the first occurrence is
  returned. If not, `NULL`. If little is an empty string, returns `big`
- **Requires:** None (`const stddef::size_t`)

### ft_atoi

`int ft_atoi(const char *nptr)`

- **Description:** Converts the initial part of the string `nptr` to an
  int. It ignores the spaces at the start an accepts one sign (+ or -)
- **Arguments:**
  - `nptr (const char *)`: Initial string
- **Return:** `(int)` Converted value or 0 on error
- **Requires:** None

### ft_calloc

`void *ft_calloc(size_t nmemb, size_t size)`

- **Description:** Allocates memory for an array of `nmemb` of `size`
  bytes, and set the memory to 0 (‘\0’). It will detect multiplication
  overflows, returning `NULL`
- **Arguments:**
  - `nmemb (size_t)`: Number of elements to allocate
  - `size (size_t)`: Number of bytes per element
- **Return:** `(void *)` Pointer to the allocated memory, or `NULL` if
  error or `size`/`nmemb` are 0
- **Requires:** `stdlib::malloc`, `libft::ft_bzero`
  (`const libft::size_t`, `limits::ULLONG_MAX`, `limits::NULL`)

### ft_strdup

`char *ft_strdup(const char *s)`

- **Description:** Duplicates `s`
- **Arguments:**
  - `s (const char *)`: String to duplicate
- **Return:** `(char *)` New allocated string. `NULL` if fails.
- **Requires:** `stdlib::malloc`, `libft::ft_strlen`
  (`const libft::size_t`)

## 2.2 Additional functions

### ft_substr

`char *ft_substr(char const *s, unsigned int start, size_t len)`

- **Description:** Calculates a string from string `s`, starting from
  the idx `start` and max length `len`
- **Arguments:**
  - `s (char const *)`: Starting string
  - `start (unsigned int)`: Starting index
  - `len (size_t)`: Max substring length
- **Return:** (`char *`) New allocated substring, NULL if memory
  allocation fails
- **Requires:** `stdlib::malloc`, `libft::(ft_strlen, ft_strlcpy)`
  (`const libft::size_t`)

### ft_strjoin

`char *ft_strjoin(char const *s1, char const *s2)`

- **Description:** Paste together strings `s1` and `s2`, creating a new
  string
- **Arguments:**
  - `s1 (char const *) s1`: First string
  - `s2 (char const *) s2`: Second string
- **Return:** (`char *`) New allocated string, NULL if memory allocation
  fails
- **Requires:** `stdlib::malloc`,
  `libft::(ft_strlen, ft_strlcpy, ft_strlcat)` (`const libft::size_t`)

### ft_strtrim

`char *ft_strtrim(char const *s1, char const *set)`

- **Description:** Trim `s1`, deleting characters from start and end of
  `s1` if they match any character from `set`, until finding a non `set`
  character
- **Arguments:**
  - `s1 (char const *)`: String to scan
  - `set (char const *)`: Set of trimable characters
- **Return:** (`char *`) New allocated string, NULL if memory allocation
  fails
- **Requires:** `stdlib::malloc`,
  `libft::(ft_strchr, ft_strlen, ft_strlcpy)` (`const libft::size_t`)

### ft_split

`char **ft_split(char const *s, char c)`

- **Description:** Creates an array of strings, splitting the string `s`
  in substrings using the character `c` as separator. The array ends
  with a `NULL` pointer
- **Arguments:**
  - `s (char const *)`: String to split
  - `c (char)`: Delimiter character
- **Return:** (`char **`) Allocated array of strings, `NULL` if any
  allocation fails
- **Requires:** `stdlib::(malloc, free)`, `libft::ft_substr`
  (`const libft::size_t`)

### ft_itoa

`char *ft_itoa(int n)`

- **Description:** Create a string from an int
- **Arguments:**
  - `n (int)`: Number to transform
- **Return:** (`char *`) Allocated string, `NULL` if allocation fails
- **Requires:** `stdlib::malloc`

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
