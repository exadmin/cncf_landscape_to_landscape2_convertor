# https://github.com/cncf/landscape2-sites/blob/main/.github/workflows/build-and-deploy.yml
# https://gallery.ecr.aws/g6m3a0y9/landscape2
FROM public.ecr.aws/g6m3a0y9/landscape2:latest

# setup properties
ARG WDIR=/home/landscape2

# mount data-files
ADD ./qubership-landscape ${WDIR}
WORKDIR "${WDIR}"
RUN landscape2 build --data-file data.yml --settings-file settings.yml --guide-file guide.yml --logos-path logos --output-dir build

# run landscape web-server on 8000 port
EXPOSE 8000/tcp
ENTRYPOINT ["landscape2", "serve", "--addr", "0.0.0.0:8000", "--landscape-dir", "build"]