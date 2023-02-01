FROM node:16

# Configure Chinese fonts for the exported PDF
RUN mkdir /usr/share/fonts/truetype/lxgwwenkai &&\
    wget https://github.com/lxgw/LxgwWenKai-Lite/releases/download/v1.250/LXGWWenKaiLite-Regular.ttf &&\
    mv *.ttf /usr/share/fonts/truetype/lxgwwenkai &&\
    fc-cache -vf &&\
    apt update &&\ 
    apt-get install -y locales &&\
    sed -ie 's/# zh_CN.UTF-8 UTF-8/zh_CN.UTF-8 UTF-8/g' /etc/locale.gen &&\
    locale-gen 
ENV LANG zh_CN.UTF-8

# Install chrome support and export pdf
RUN apt update &&\
    apt install -y gconf-service libxext6 libxfixes3 libxi6 libxrandr2 libxrender1 \
                libcairo2 libcups2 libdbus-1-3 libexpat1 libfontconfig1 libgcc1 \
                libgconf-2-4 libgdk-pixbuf2.0-0 libglib2.0-0 libgtk-3-0 libnspr4 \
                libpango-1.0-0 libpangocairo-1.0-0 libstdc++6 libx11-6 libx11-xcb1 \
                libxcb1 libxcomposite1 libxcursor1 libxdamage1 libxss1 libxtst6 \
                libappindicator1 libnss3 libasound2 libatk1.0-0 libc6 ca-certificates \
                fonts-liberation lsb-release xdg-utils

# Running locally

# WORKDIR /app

# COPY . ./
# RUN cp -r docs ../ && npm install

# EXPOSE 3000
# ENTRYPOINT [ "npm", "run", "dev" ]