# strictDC
script sample:

#!/bin/csh

#$ -M jliu16@nd.edu	 # Email address for job notification
#$ -m abe		 # Send mail when job begins, ends and aborts
#$ -pe smp 4		 # Specify parallel environment and legal core size
#$ -q gpu		 # Specify queue
#$ -N GeTestS1	         # Specify job name

module load python cuda/8.0 tensorflow/0.12-python2        # Required modules

#python main.py --dataset ibmpg1t1/strain --input_width=541 --output_width=541 --c_dim=1 > rec/rec_sSample100_1

python main_5.py --dataset ibmpg1t1/strain --input_width=541 --output_width=541 --c_dim=1 > rec/rec_sSample1k_2

#python SensorCount.py -s samples/s_100r_1

#python Cover_1.py -s ../data/ibmpg1t1/stest -r sensors/sensor_from_s_100r_1_0.9

#python SensorCount.py -s samples/s_1kr_1

#python Cover_1.py -s ../data/ibmpg1t1/stest -r sensors/sensor_from_s_1kr_1_0.9
