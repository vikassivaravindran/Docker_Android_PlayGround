FROM openjdk:8
LABEL maintainer="vikassivaravindran@gmail.com"

#Environment Setup
ENV SDK_URL="https://dl.google.com/android/repository/sdk-tools-linux-3859397.zip" \
	ANDROID_HOME="/usr/local/android-sdk" \
	ANDROID_VERSION=26 \
	ANDROID_BUILD_TOOLS_VERSION=26.0.2

#Download Android SDK
RUN mkdir "$ANDROID_HOME" \
	&& cd "$ANDROID_HOME" \
	&& curl -o sdk.zip $SDK_URL \
	&& unzip sdk.zip \
	&& rm sdk.zip \
	&& yes | $ANDROID_HOME/tools/bin/sdkmanager --licenses

#Install Android SDK Build Tools and Libraries.
RUN $ANDROID_HOME/tools/bin/sdkmanager --update
RUN $ANDROID_HOME/tools/bin/sdkmanager "build-tools;${ANDROID_BUILD_TOOLS_VERSION}" \
	"platforms;android-${ANDROID_VERSION}" \
	"platform-tools"



