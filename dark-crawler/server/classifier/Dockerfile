FROM node:10

WORKDIR /app/

RUN apt-get update && apt-get install -y \
	libcairo2-dev \
	libjpeg-dev \
	libpango1.0-dev \
	libgif-dev \
	libpng-dev \
	build-essential \
	g++

COPY ./server/classifier/package.json /app

RUN yarn global add supervisor
RUN yarn

COPY ./server/classifier/src /app/src

EXPOSE 8080

CMD ["yarn", "run", "serve"]