NAME = convert
CC = c++
CFLAGS = -g -Wall -Wextra -Werror -std=c++98
SRC = Serializer.cpp main.cpp
OBJ = $(SRC:.cpp=.o)

all: $(NAME)

$(NAME): $(OBJ)
	$(CC) $(CFLAGS) $(SRC) -o $(NAME)
	@echo "\033[1;32mBuild completed successfully!\033[0m"

clean:
	@rm -f $(OBJ)
	@echo "\033[1;31mObject files removed!\033[0m"

fclean: clean
	@rm -f $(NAME)
	@echo "\033[1;31mExecutable removed!\033[0m"

re: fclean all
r : re