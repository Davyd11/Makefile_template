NAME = a.out

# Source files
SRCS = main.cpp

# Colors for console output
BLU = \\033[0;34m
GRN = \\033[0;32m
RED = \\033[0;31m
RESET = \\033[0m

# Object files
OBJS = $(SRCS:.cpp=.o)

# Compiler and its options
CXX = c++ --std=c++98
CXXFLAGS = -Wall -Wextra -Werror -g3 -fsanitize=address
RM = rm -f

# Build targets
.PHONY: all clean fclean re

# Default target
all: $(NAME)

# Compile the program
$(NAME): $(OBJS)
	@echo "$(BLU)Building $(NAME)$(RESET)"
	$(CXX) $(CXXFLAGS) -o $(NAME) $(OBJS)

# Clean object files
clean:
	@echo "$(RED)Cleaning up object files$(RESET)"
	$(RM) $(OBJS)

# Full clean, including the executable
fclean: clean
	@echo "$(RED)Removing executable $(NAME)$(RESET)"
	$(RM) $(NAME)

# Rebuild everything
re: fclean all

# Additional rules for convenience
run: all
	./$(NAME)

