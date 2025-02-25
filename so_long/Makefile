SRCS =  mand/so_long.c \
		mand/get_next_line/get_next_line.c \
		mand/ft_get_map.c \
		mand/ft_tools.c \
		mand/ft_exit.c  \
		mand/ft_get_map_dimention.c \
		mand/ft_get_img_data.c \
		mand/ft_drow_map.c \
		mand/ft_first_move.c \
		mand/ft_get_player_position.c \
		mand/ft_valid_map.c \
		mand/ft_cleanup_game.c \
		mand/ft_checking_tools.c \
		mand/ft_puterror.c \
		mand/ft_put_image.c \
		mand/ft_moving_player.c \

BSRCS = bonus/so_long_bonus.c \
		bonus/get_next_line_bonus/get_next_line.c \
		bonus/ft_get_map_bonus.c \
		bonus/ft_tools_bonus.c \
		bonus/ft_exit_bonus.c  \
		bonus/ft_get_map_dimention_bonus.c \
		bonus/ft_get_img_data_bonus.c \
		bonus/ft_drow_map_bonus.c \
		bonus/ft_first_move_bonus.c \
		bonus/ft_get_player_position_bonus.c \
		bonus/ft_valid_map_bonus.c \
		bonus/ft_cleanup_game_bonus.c \
		bonus/ft_checking_tools_bonus.c \
		bonus/ft_puterror_bonus.c \
		bonus/ft_put_image_bonus.c \
		bonus/ft_moving_enemy.c \
		bonus/ft_moving_player_bonus.c \
		bonus/ft_put_open_door.c \
		bonus/ft_count_collectibles.c \
		bonus/ft_check_components.c \
	
CC 		= cc

CFLAGS 	=  -Wall -Wextra -Werror  -Wunused-function -fsanitize=address

MLX = -L/home/eel-garo/include/mlx/ -lmlx -lX11 -lXext


OBJS = $(SRCS:.c=.o)
BOBJS = $(BSRCS:.c=.o)

INCLUDES = -I includes -I ft_printf -I /home/eel-garo/include/mlx/

FT_PRINTF_DIR = ft_printf

LIBFT_DIR = libft

LIBFT_LIB = $(LIBFT_DIR)/libft.a

FT_PRINTF_LIB = $(FT_PRINTF_DIR)/libftprintf.a

FT_GET_NEXT_LINE_DIR = get_next_line

NAME 	= so_long
B_NAME  = so_long_bonus

all : $(FT_PRINTF_LIB) $(LIBFT_LIB) $(NAME)

bonus: $(FT_PRINTF_LIB) $(LIBFT_LIB) $(B_NAME)

$(FT_PRINTF_LIB):
	$(MAKE) -C $(FT_PRINTF_DIR)

$(LIBFT_LIB):
	$(MAKE) -C $(LIBFT_DIR)

$(NAME): $(OBJS)
	$(CC) $(CFLAGS) $(OBJS) $(MLX) $(FT_PRINTF_LIB) $(LIBFT_LIB) -o $(NAME)                     

$(B_NAME): $(BOBJS)
	$(CC) $(CFLAGS) $(BOBJS) $(MLX) $(FT_PRINTF_LIB) $(LIBFT_LIB) -o $(B_NAME)     

$(OBJS): %.o:%.c mand/so_long.h
	$(CC) $(CFLAGS) $(INCLUDES) -c $< -o $@

$(BOBJS): %.o:%.c bonus/so_long_bonus.h
	$(CC) $(CFLAGS) $(INCLUDES) -c $< -o $@

clean:
	$(MAKE) clean -C $(FT_PRINTF_DIR)
	$(MAKE) clean -C $(LIBFT_DIR)
	rm -f $(OBJS) $(BOBJS)

fclean: clean
	$(MAKE) fclean -C $(FT_PRINTF_DIR)
	$(MAKE) fclean -C $(LIBFT_DIR)
	rm -f $(NAME) $(B_NAME)


re: fclean all
