# Copyright 2018 Google Inc.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#
################################################################################

FROM gcr.io/oss-fuzz-base/base-builder
MAINTAINER janne-vlc@jannau.net
RUN apt-get update && apt-get install -y curl python3-pip wget && \
    pip3 install meson ninja
RUN wget http://www.nasm.us/pub/nasm/releasebuilds/2.13.02/nasm-2.13.02.tar.gz
RUN curl --silent -O https://storage.googleapis.com/aom-test-data/fuzzer/dec_fuzzer_seed_corpus.zip
RUN curl --silent -O https://jannau.net/dav1d_fuzzer_seed_corpus.zip
RUN git clone --depth 1 https://code.videolan.org/videolan/dav1d.git dav1d
WORKDIR dav1d
COPY build.sh fuzzer.options $SRC/
