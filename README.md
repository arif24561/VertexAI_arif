# VertexAI_arif
1  gcloud auth list
2  gcloud config list projec
3  gcloud config set project vertex-ai-329015
4  gcloud config list projec
5  echo $GOOGLE_CLOUD_PROJECT
6  gcloud services enable compute.googleapis.com                                containerregistry.googleapis.com                         aiplatform.googleapis.com
7  BUCKET_NAME=gs://$GOOGLE_CLOUD_PROJECT-bucket
8  gsutil mb -l us-central1 $BUCKET_NAME
9  alias python=python3
10  mkdir mpg
11  cd mpg
12  touch Dockerfile
13  mkdir trainer
14  touch trainer/train.py
15  vim Dockerfile
16  vim trainer/train.py
17  sed -i "s|BUCKET_NAME|$BUCKET_NAME|g" trainer/train.py
18  vim trainer/train.py
19  IMAGE_URI="gcr.io/$GOOGLE_CLOUD_PROJECT/mpg:v1"
20  docker build ./ -t $IMAGE_URI
21  docker push $IMAGE_URI
22  vim trainer/train.py
23  pip3 install google-cloud-aiplatform --upgrade --user
24  vim deploy.py
25  python3 deploy.py | tee deploy-output.txt
26  vim deploy.py
27  python3 deploy.py | tee deploy-output.txt
28  ENDPOINT=$(cat deploy-output.txt | sed -nre 's:.*Resource name\: (.*):\1:p' | tail -1)
29  sed -i "s|ENDPOINT_STRING|$ENDPOINT|g" predict.py
30  ls
31  vim predict.py
32  sed -i "s|ENDPOINT_STRING|$ENDPOINT|g" predict.py
33  vim predict.py
34  python3 predict.py
35  history
