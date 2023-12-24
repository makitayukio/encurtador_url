# create image
FROM python:3.10 AS backend

# create main directory
WORKDIR /usr/src/server

# copy local folder content
COPY . .

# upgrade pip version and install python dependencies from file
RUN pip install --upgrade pip && pip install -r requirements.txt

# bind mount local directory to container
RUN --mount=type=bind,source=.,target=usr/src/server

# expose port used for server
EXPOSE 5000

# run python script
CMD ["flask", "run", "--reload", "--host=0.0.0.0"]
