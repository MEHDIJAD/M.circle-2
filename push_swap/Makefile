SRCS   = 	 mand/push_swap.c \
	     	 mand/ft_check_input.c \
		 	 mand/ft_fill_stack_a.c \
		 	 mand/ft_check_double.c \
		 	 mand/ft_sort_list.c \
		 	 mand/ft_index_stack_a.c \
		 	 mand/ft_find_min.c \
		 	 mand/ft_find_max.c \
		 	 mand/ft_sorted.c \
		 	 mand/ops/ft_op_swap.c \
		 	 mand/ops/ft_op_rotate.c \
		 	 mand/ops/ft_op_rrotate.c \
		 	 mand/ops/ft_op_push.c \
		 	 mand/algo/ft_sort_three.c \
		 	 mand/algo/ft_sort_four.c \
		 	 mand/algo/ft_sort_five.c \
		 	 mand/algo/ft_sort_mid.c \

SRCS_BONUS = bonus/checker_bonus.c \
             bonus/ft_op_rr_bonus.c \
             bonus/ft_op_rrr_bonus.c \
             bonus/ft_op_ss_bonus.c \
             bonus/ft_sort_with_arg_bonus.c \
			 bonus/ops/ft_op_swap_bonus.c \
		 	 bonus/ops/ft_op_rotate_bonus.c \
		 	 bonus/ops/ft_op_rrotate_bonus.c \
		 	 bonus/ops/ft_op_push_bonus.c \
			 bonus/ft_check_input_bonus.c \
			 bonus/ft_fill_stack_a_bonus.c \
			 bonus/ft_check_double_bonus.c \
			 bonus/ft_index_stack_a_bonus.c \
			 bonus/ft_sorted_bonus.c \
			 bonus/get_next_line/get_next_line.c \


OBJS   = $(SRCS:.c=.o)
OBJS_BONUS = $(SRCS_BONUS:.c=.o)

FT_PRINTF_DIR = ft_printf

FT_PRINTF_LIB = $(FT_PRINTF_DIR)/libftprintf.a

LIBFT_DIR = libft

LIBFT_LIB = $(LIBFT_DIR)/libft.a

CC     = cc 
CFLAGS = -Wall -Wextra -Werror
LIBC   = ar rc
RM	   = rm -rf
NAME   = push_swap
NAME_BONUS = checker

all: $(FT_PRINTF_LIB)  $(LIBFT_LIB) $(NAME)

$(FT_PRINTF_LIB):
	$(MAKE) -C $(FT_PRINTF_DIR)

$(LIBFT_LIB):
	$(MAKE) -C $(LIBFT_DIR)

$(NAME): $(OBJS)
	$(CC) $(CFLAGS) $(OBJS) $(FT_PRINTF_LIB) $(LIBFT_LIB) -o $(NAME)

$(OBJS): %.o:%.c mand/push_swap.h
	$(CC) $(CFLAGS) -c  $< -o $@

$(OBJS_BONUS): %.o:%.c bonus/push_swap_bonus.h
	$(CC) $(CFLAGS) -c  $< -o $@

bonus: $(FT_PRINTF_LIB) $(LIBFT_LIB) $(NAME_BONUS)

$(NAME_BONUS): $(OBJS_BONUS)
	$(CC) $(CFLAGS) $(OBJS_BONUS) $(FT_PRINTF_LIB) $(LIBFT_LIB) -o $(NAME_BONUS)

clean:
	$(MAKE) clean -C $(FT_PRINTF_DIR)
	$(MAKE) clean -C $(LIBFT_DIR)
	$(RM) $(OBJS) $(OBJS_BONUS)

fclean: clean
	$(MAKE) fclean -C $(FT_PRINTF_DIR)
	$(MAKE) fclean -C $(LIBFT_DIR)
	$(RM) $(NAME) $(NAME_BONUS)

re: fclean all




