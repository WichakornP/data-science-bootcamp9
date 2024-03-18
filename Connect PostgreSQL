# Connect R to PostgreSQL----------------------
# 1.open connection to SQL
# 2.display table lists, create tables, remove tables
# 3.close connection 

library(RPostgreSQL)
library(tidyverse)

# create dataframe
products <- tribble(
  ~id, ~product_name,
  1, "Apple",
  2, "Orange",
  3, "Watermelon"
)

# connect to PostgreSQL
con <- dbConnect(
  PostgreSQL(),                       # SQL server
  host = "floppy.db.elephantsql.com", # IP address database
  dbname = "pjkvzzxu",                # database name
  user = "pjkvzzxu",                  # user name
  password = "v8SynMEMJQQ_yWOl3YtI-20jyWa_Fj49",
  port = 5432                         # RPostgreSQL port
)

# display list of tables
dbListTables(con)

# create table from existing dataframe
dbWriteTable(con, "products", products) 

# get data by using query like SQL
df <- dbGetQuery(con, "select id, product_name from products")
df

# remove table
dbRemoveTable(con, "products")

# close connection
dbDisconnect(con)
