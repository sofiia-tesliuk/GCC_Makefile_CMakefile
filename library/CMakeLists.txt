libjpeg_SRCS  = $(foreach d, $(wildcard $(addprefix $(d)/*,*.c)))

add_library(libjpeg STATIC ${libjpeg_SRCS})
add_library(libjpeg-shared SHARED ${libjpeg_SRCS})
set_target_properties(libjpeg-shared PROPERTIES OUTPUT_NAME libjpeg)
