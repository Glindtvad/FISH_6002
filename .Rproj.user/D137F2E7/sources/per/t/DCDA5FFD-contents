
# ---------------------- Data Import  ------------------------------------- #

WD <- getwd()
list.files()

Raw.df <- read.csv(".\\Data\\RawData.csv")

HH.df <- Raw.df[Raw.df$RecordType == "HH",]
HH.colnames <- colnames(HH.df)

HL.colnames <- unlist(Raw.df[nrow(HH.df)+1,])
HL.df <- Raw.df[Raw.df$RecordType == "HL",]

CA.colnames <- unlist(Raw.df[nrow(HH.df)+nrow(HL.df)+2,])
CA.df <- Raw.df[Raw.df$RecordType == "CA",]

colnames(HL.df) <- HL.colnames
colnames(CA.df) <- CA.colnames


# ---------------------- Libraries  ------------------------------------- #

library("tidyverse")
# library("rgdal")

# ---------------------- Manipulation  ------------------------------------- #

HL.colnames <- HL.colnames[!is.na(HL.colnames)]
HL.colnames <- HL.colnames[1:30]
HL.df <- HL.df[,1:length(HL.colnames)]

CA.colnames <- CA.colnames[!is.na(CA.colnames)]
CA.df <- CA.df[,1:length(CA.colnames)]

HL.df$ID <- paste(HL.df$Country, HL.df$Ship, HL.df$HaulNo, HL.df$Year, sep = "_")
CA.df$ID <- paste(CA.df$Country, CA.df$Ship, CA.df$HaulNo, CA.df$Year, sep = "_")

HL_NO_Haul_5_Year_2005 <- HL.df[HL.df$Year == 2005,]
HL_NO_Haul_5_Year_2005 <- HL_NO_Haul_5_Year_2005[HL_NO_Haul_5_Year_2005$Country == "NO",]
HL_NO_Haul_5_Year_2005 <- HL_NO_Haul_5_Year_2005[HL_NO_Haul_5_Year_2005$HaulNo == 5,]
HL_NO_Haul_5_Year_2005 <- HL_NO_Haul_5_Year_2005[HL_NO_Haul_5_Year_2005$ScientificName_WoRMS == "Gadus morhua",]

CA_NO_Haul_5_Year_2005 <- CA.df[CA.df$Year == 2005,]
CA_NO_Haul_5_Year_2005 <- CA_NO_Haul_5_Year_2005[CA_NO_Haul_5_Year_2005$Country == "NO",]
CA_NO_Haul_5_Year_2005 <- CA_NO_Haul_5_Year_2005[CA_NO_Haul_5_Year_2005$HaulNo == 5,]
CA_NO_Haul_5_Year_2005 <- CA_NO_Haul_5_Year_2005[CA_NO_Haul_5_Year_2005$ScientificName_WoRMS == "Gadus morhua",]

Raw.df[44668,]
# ---------------------- Maps ------------------------------------- #



