# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: dkrause- <marvin@42.fr>                    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2018/06/07 20:10:47 by dkrause-          #+#    #+#              #
#    Updated: 2018/06/07 20:10:48 by dkrause-         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

NAME =	libgfx.a
FLAGS =	-Wall -Wextra -Werror
CC = 	gcc
ODIR =	bin/
IDIR = 
SRC =
OBJ =	$(SRC:.c=.o)
EXT =	$(IDIR)$(NAME:.a=.h)

EXT +=	Makefile

SRC	+=	ft_drawline.c \
		matrix_math.c \
		transform_matrix.c \
		initializers.c

O =		$(addprefix $(ODIR), $(OBJ))

MLXINC	= -I../minilibx
LFTINC	= -I../libft

all: $(NAME)

love: all

norm:
	norminette $(S)

$(NAME): $(O) $(EXT)
	@ar rc $(NAME) $(O)
	@ranlib $(NAME)

$(ODIR)%.o: %.c $(EXT)
	@echo "-> Compiling $<..."
	@$(CC) $(FLAGS) $(MLXINC) $(LFTINC) -c $< -o $@

$(O): | ./bin

./bin:
	@mkdir $(ODIR)

clean:
	@echo "-> Cleaning libgfx object files..."
	@rm -f bin/*.o

fclean: clean
	@echo "-> Cleaning $(NAME)..."
	@rm -f $(NAME) 

re: fclean all

.PHONY: all clean fclean re norm
