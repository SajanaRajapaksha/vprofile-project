FROM nginx
LABEL "Project" = "vprofile"
LABEL "Author" = "sajana"

#remove default configuration files
RUN rm -rf /etc/nginx/conf.d/default.conf
COPY nginvproapp.conf /etc/nginx/conf.d/vproapp.conf