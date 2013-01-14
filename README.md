# Modified original spark to handle S3 files.

To auth, set these environment variables:

export AWS_ACCESS_KEY_ID=<id> 
export AWS_SECRET_ACCESS_KEY=<key> 

# Launch cluster

Launch cluster like so:


./spark-ec2 --key-pair=<keypair> --identity-file=<key-file> --environment /home/mfg/enviroment.sh --slaves=2 --instance-type=m1.medium --region=eu-west-1 --user=ubuntu --ami=ami-9ec1ccea --spot-price=0.033 --cluster-type=standalone launch <cluster-name> 

The environment file is just a bash script that contains the commands to set the above environment variables:

If it goes wrong, resume by adding the --resume parameter.

# Run job

Run ./spark-ec2 --key-pair=<keypair> --identity-file=<key-file> login <cluster-name> 

# End job

./spark-ec2 destroy <cluster-name>
