# cncf_landscape_to_landscape2_convertor

# How to build
cd ./production
sudo docker build . -t ${IMAGE_NAME:VERSION}

# How to run locally (tested in WSL/Ubuntu)
sudo docker run -d -p 8000:8000 ${IMAGE_NAME:VERSION}
