# Welcome
This website contain a meme I made using the R code.

## My meme!
![](my_meme.png)

A summary of my inspiration for the meme is:

1. I think of a meme I liked
2. I copied it, use iamge found online

## R Code
library(magick)
play <- image_read("https://previews.123rf.com/images/lenm/lenm1409/lenm140900111/31689305-illustration-featuring-a-group-of-boys-playing-soccer.jpg") %>%
  image_scale(500)

image_write(play, "my_meme1.png")
playtext <- image_blank(width = 500, 
                        height = 500, 
                        color = "#000000") %>%
  image_annotate(text = "Assignment due Next Week",
                 color = "#FFFFFF",
                 size = 20,
                 font = "Impact",
                 gravity = "center")
study <- image_read("http://img95.699pic.com/element/40023/6784.png_300.png") %>%
  image_scale(500)
image_write(study, "my_meme2.png")




studytext <- image_blank(width = 500, 
                         height = 500, 
                         color = "#000000") %>%
  image_annotate(text = "Assignment due Tomorrow",
                 color = "#FFFFFF",
                 size = 20,
                 font = "Impact",
                 gravity = "center")

first_row <- c(play, playtext) %>%
  image_append()

second_row <- c(study, studytext) %>%
  image_append()

c(first_row, second_row) %>%
  image_append(stack = TRUE)
  

