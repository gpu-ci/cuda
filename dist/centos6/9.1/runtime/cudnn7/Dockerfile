ARG IMAGE_NAME
FROM ${IMAGE_NAME}:9.1-runtime-centos6
LABEL maintainer "NVIDIA CORPORATION <sw-cuda-installer@nvidia.com>"

ENV CUDNN_VERSION 7.1.2.21
LABEL com.nvidia.cudnn.version="${CUDNN_VERSION}"

# cuDNN license: https://developer.nvidia.com/cudnn/license_agreement
RUN CUDNN_DOWNLOAD_SUM=c61000ed700bc5a009bc2e135bbdf736c9743212b2174a2fc9018a66cc0979ec && \
    curl -fsSL http://developer.download.nvidia.com/compute/redist/cudnn/v7.1.2/cudnn-9.1-linux-x64-v7.1.tgz -O && \
    echo "$CUDNN_DOWNLOAD_SUM  cudnn-9.1-linux-x64-v7.1.tgz" | sha256sum -c - && \
    tar --no-same-owner -xzf cudnn-9.1-linux-x64-v7.1.tgz -C /usr/local --wildcards 'cuda/lib64/libcudnn.so.*' && \
    rm cudnn-9.1-linux-x64-v7.1.tgz && \
    ldconfig
