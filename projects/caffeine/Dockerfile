# Copyright 2025 Google LLC
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

FROM gcr.io/oss-fuzz-base/base-builder-jvm

RUN git clone --depth 1 https://github.com/ben-manes/caffeine

RUN apt update && apt install -y openjdk-11-jdk-headless openjdk-21-jdk-headless
ENV JAVA_HOME /usr/lib/jvm/java-21-openjdk-amd64

COPY build.sh $SRC/
COPY *Fuzzer.java $SRC/
WORKDIR $SRC/caffeine
