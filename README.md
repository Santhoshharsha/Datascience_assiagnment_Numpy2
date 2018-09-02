# Datascience_assiagnment_Numpy2
Datascience_assiagnment_Numpy2
# # 1.Given a sequence of n values x1, x2, ..., xn and a window size k>0, the k-th moving average of  the given sequence is defined as follows: The moving average sequence has n-k+1 elements as shown below. The moving averages with k=4 of a ten-value sequence (n=10) is shown below
# i 1 2 3 4 5 6 7 8 9 10
#===== == == == == == == == == == ==
#Input 10 20 30 40 50 60 70 80 90 100
# y1 25 = (10+20+30+40)/4
# y2 35 = (20+30+40+50)/4
# y3 45 = (30+40+50+60)/4
# y4 55 = (40+50+60+70)/4
# y5 65 = (50+60+70+80)/4
# y6 75 = (60+70+80+90)/4
# y7 85 = (70+80+90+100)/4
# Thus, the moving average sequence has n-k+1=10-4+1=7 values.
# Problem Statement:
# Write a function to find moving average in an array over a window: Test it over [3, 5, 7, 2, 8, 10, 11, 65, 72, 81, 99, 100, 150] and window of 3.

List_a = [3,5,7,2,8,10,11,65,72,81,99,100,150]

moving_seq = 3
cummlative_sum , moving_average = [0],[]

def Moving_average_fun(List_a, moveing_seq): 
    N =  moving_seq 
    for i , j  in enumerate(List_a,1): 
        cummlative_sum.append(cummlative_sum[i-1] + j) 

        if i>=N: 
            moving_ave = round((cummlative_sum[i] - cummlative_sum[i-N])/N,2) 

            moving_average.append(moving_ave) 
    return (moving_average), len(moving_average) 

Result_fun = Moving_average_fun(List_a,moving_seq)

print ("----"*10)
print (" User defined List :-\n {} \n User Define Window Size :-\t {} ".format(List_a,moving_seq))
print ("----"*10)
print (" Result Using above defined Funtion :\t")
print (" Moving average value :\n",Result_fun[0])
print (" Moving average seques has :- {}, values".format(Result_fun[1]))
print ("----"*10)
