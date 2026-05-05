# Code Chunk 
For my self-contained code chunk, I use data from the best_dog.xlsx data set, with the core measurements being breed type and lifetime costs
per breed. The first part of the chunk loads the libraries that I need, and then opens the dataset I use. The second part of the dataset creates a boxplot. 
First, the aesthetic mapping function maps type on the x asix, and maps lifetime costs on the y axis. The final aesthetic mapping fills each box with a different color
based on type. Secondly, the labeleling function titles the graph "Dog Breed Costs - By Type," titles the x - axis "Type," and titles the y axis "Lifetime costs." Next, the 
theme command fucntion angles the "type" names on the x axis to 45 degree angles and adjusts the position of the type names slightly down for readability. Finally, 
the scale_y_continous command sets y axis limits between 13000 and 30000, and sets the ticks as 1,000 apart. 
## Code
library(tidyverse) 
library(readxl) 
data <- read_excel("best_dog.xlsx", sheet = 2) 
data |> 
  ggplot(aes(x = type, y = lifetime_cost, fill = type)) +
  geom_boxplot(show.legend = FALSE, na.rm = TRUE) +
  labs(title = "Dog Breed Costs - By Type",
       x = "Type",
       y = "Lifetime Costs") +
  theme(axis.text.x = element_text(angle = 45, hjust = 1)) +
  scale_y_continuous(breaks = seq(13000, 30000, by = 1000)) 

  ## Output
  - Includes an image of the output and a link to the html output.
  
  http://localhost:3958/best_dog_files/figure-html/Self-contained%20code%20chunk-1.png<img width="1344" height="960" alt="image" src="https://github.com/user-attachments/assets/d87c2962-923c-4cad-87be-b8d123b8d391" />
  
http://localhost:3958/best_dog.html
