FROM nginx:alpine

#copy files to the nginx html directory
COPY . /usr/share/nginx/html

#set ownership and permissions
RUN chmode -R 755 /usr/share/nginx/html

Expose 80
