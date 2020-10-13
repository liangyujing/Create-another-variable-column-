```
###if else
#membership_gender
my_data_gender_A$membership <- ifelse(my_data_gender_A$gender==1 & my_data_gender_A$variable=="AccMenPos", "1","0")
my_data_gender_A$membership[my_data_gender_A$gender==1 & my_data_gender_A$variable=="AccMenNeg"] <- 1
my_data_gender_A$membership[my_data_gender_A$gender==2 & my_data_gender_A$variable=="AccWomenPos"] <- 1
my_data_gender_A$membership[my_data_gender_A$gender==2 & my_data_gender_A$variable=="AccWomenNeg"] <- 1
my_data_gender_A$membership<- factor(my_data_gender_A$membership,c(1,0),labels = c("Ingroup","Outgroup"))

#valence
my_data_gender_A$valence <- ifelse(my_data_gender_A$variable=="AccMenPos", "1","0")
my_data_gender_A$valence[my_data_gender_A$variable=="AccWomenPos"] <- 1
my_data_gender_A$valence<- factor(my_data_gender_A$valence,c(1,0),labels = c("Positive","Negative"))
summary(my_data_gender_A)

###membership_age
my_data_age_T$membership <- ifelse(my_data_age_T$agegroup_subj==1 & my_data_age_T$variable=="TruthYoungPos", "1","2")
my_data_age_T$membership[my_data_age_T$agegroup_subj==1 & my_data_age_T$variable=="TruthYoungNeg"] <- 1
my_data_age_T$membership[my_data_age_T$agegroup_subj==3 & my_data_age_T$variable=="TruthOldPos"] <- 1
my_data_age_T$membership[my_data_age_T$agegroup_subj==3 & my_data_age_T$variable=="TruthOldNeg"] <- 1
##outgroup
my_data_age_T$membership[my_data_age_T$agegroup_subj==1 & my_data_age_T$variable=="TruthOldPos"] <- 0
my_data_age_T$membership[my_data_age_T$agegroup_subj==1 & my_data_age_T$variable=="TruthOldNeg"] <- 0
my_data_age_T$membership[my_data_age_T$agegroup_subj==3 & my_data_age_T$variable=="TruthYoungPos"] <- 0
my_data_age_T$membership[my_data_age_T$agegroup_subj==3 & my_data_age_T$variable=="TruthYoungNeg"] <- 0

my_data_age_T$membership<- factor(my_data_age_T$membership,c(1,0,2),labels = c("Ingroup","Outgroup","Middlegroup"))
```
