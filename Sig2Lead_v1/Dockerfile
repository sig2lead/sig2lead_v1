# FROM rocker/shiny:3.4.3
FROM rocker/shiny:4.0.3

RUN apt-get update && apt-get install -y sudo libcurl4-gnutls-dev libxml2-dev libssl-dev git; 

RUN rm -r /srv/shiny-server; 

RUN mkdir -p /var/lib/shiny-server/bookmarks/shiny; 

RUN sed -i 's/3838/3838 0.0.0.0/' /etc/shiny-server/shiny-server.conf
RUN R -e "install.packages(pkgs=c('tidyverse','shinydashboard'))"

RUN R -e "install.packages('shinydashboard')"

RUN R -e "install.packages('lubridate')"
RUN R -e "install.packages('magrittr')"
RUN R -e "install.packages('glue')"

RUN apt-get install -y libudunits2-dev

RUN R -e "install.packages(c('shiny', 'shinyjs','ggplot2','plotly','httr','jsonlite','DT','visNetwork','plyr','dendextend','colorspace','ggforce','rlist','scatterpie','ggrepel','bazar','XML','RCurl','bitops','scrapeR','igraph','circlize','enrichR','readr', 'doBy'))"

RUN R -e "install.packages(c('dplyr','gplots'))"



RUN sudo apt-get install libopenbabel-dev -y
RUN R -e "install.packages('BiocManager')"
RUN R -e "BiocManager::install(version = '3.12')"
RUN apt-get install -y libeigen3-dev librsvg2-bin
RUN R -e "BiocManager::install(c('ChemmineOB', 'ChemmineR'))"


RUN R -e "install.packages('ggforce')"
RUN R -e "install.packages('scatterpie')"

RUN apt-get install -y libglpk-dev

RUN mkdir -p /srv/shiny-server/userfile;


#copy the app to the image

COPY ./app/Sig2Lead_Backend.Rproj /srv/shiny-server/
COPY ./app/ui.R /srv/shiny-server/
RUN mkdir /srv/shiny-server/files/
RUN mkdir /srv/shiny-server/www/
#RUN mkdir /srv/shiny-server/www/Sig2Lead_Manual_docker_v1_files/
COPY ./app/www/s2l.png /srv/shiny-server/www/
COPY ./app/www/sig2lead_rev.png /srv/shiny-server/www/
#COPY ./app/www/Sig2Lead_Manual_single_page.mht /srv/shiny-server/www/
#COPY ./app/www/Sig2Lead_Manual_v2.htm /srv/shiny-server/www/

############### Old User Manual ###########################

#RUN mkdir /srv/shiny-server/www/Sig2Lead_Manual_docker_v1_files/
#COPY ./app/www/Sig2Lead_Manual_docker_v1.htm /srv/shiny-server/www/
#COPY ./app/www/Sig2Lead_Manual_docker_v1_files/image001.png /srv/shiny-server/www/Sig2Lead_Manual_docker_v1_files/
#COPY ./app/www/Sig2Lead_Manual_docker_v1_files/image002.jpg /srv/shiny-server/www/Sig2Lead_Manual_docker_v1_files/
#COPY ./app/www/Sig2Lead_Manual_docker_v1_files/image003.png /srv/shiny-server/www/Sig2Lead_Manual_docker_v1_files/
#COPY ./app/www/Sig2Lead_Manual_docker_v1_files/image004.jpg /srv/shiny-server/www/Sig2Lead_Manual_docker_v1_files/
#COPY ./app/www/Sig2Lead_Manual_docker_v1_files/image005.png /srv/shiny-server/www/Sig2Lead_Manual_docker_v1_files/
#COPY ./app/www/Sig2Lead_Manual_docker_v1_files/image006.jpg /srv/shiny-server/www/Sig2Lead_Manual_docker_v1_files/
##########################################################################################################

RUN mkdir /srv/shiny-server/www/Sig2Lead_v1_user_manual_for_help_files/
COPY ./app/www/Sig2Lead_v1_user_manual_for_help.htm /srv/shiny-server/www/
COPY ./app/www/Sig2Lead_v1_user_manual_for_help_files/image001.png /srv/shiny-server/www/Sig2Lead_v1_user_manual_for_help_files/
COPY ./app/www/Sig2Lead_v1_user_manual_for_help_files/image002.png /srv/shiny-server/www/Sig2Lead_v1_user_manual_for_help_files/
COPY ./app/www/Sig2Lead_v1_user_manual_for_help_files/image003.jpg /srv/shiny-server/www/Sig2Lead_v1_user_manual_for_help_files/
COPY ./app/www/Sig2Lead_v1_user_manual_for_help_files/image004.png /srv/shiny-server/www/Sig2Lead_v1_user_manual_for_help_files/
COPY ./app/www/Sig2Lead_v1_user_manual_for_help_files/image005.jpg /srv/shiny-server/www/Sig2Lead_v1_user_manual_for_help_files/
COPY ./app/www/Sig2Lead_v1_user_manual_for_help_files/image006.png /srv/shiny-server/www/Sig2Lead_v1_user_manual_for_help_files/
COPY ./app/www/Sig2Lead_v1_user_manual_for_help_files/image007.jpg /srv/shiny-server/www/Sig2Lead_v1_user_manual_for_help_files/
COPY ./app/www/Sig2Lead_v1_user_manual_for_help_files/image008.png /srv/shiny-server/www/Sig2Lead_v1_user_manual_for_help_files/
COPY ./app/www/Sig2Lead_v1_user_manual_for_help_files/image009.jpg /srv/shiny-server/www/Sig2Lead_v1_user_manual_for_help_files/
COPY ./app/www/Sig2Lead_v1_user_manual_for_help_files/image010.png /srv/shiny-server/www/Sig2Lead_v1_user_manual_for_help_files/
COPY ./app/www/Sig2Lead_v1_user_manual_for_help_files/image011.jpg /srv/shiny-server/www/Sig2Lead_v1_user_manual_for_help_files/
COPY ./app/www/Sig2Lead_v1_user_manual_for_help_files/image012.png /srv/shiny-server/www/Sig2Lead_v1_user_manual_for_help_files/
COPY ./app/www/Sig2Lead_v1_user_manual_for_help_files/image013.jpg /srv/shiny-server/www/Sig2Lead_v1_user_manual_for_help_files/
COPY ./app/www/Sig2Lead_v1_user_manual_for_help_files/image014.png /srv/shiny-server/www/Sig2Lead_v1_user_manual_for_help_files/
COPY ./app/www/Sig2Lead_v1_user_manual_for_help_files/image015.jpg /srv/shiny-server/www/Sig2Lead_v1_user_manual_for_help_files/
COPY ./app/www/Sig2Lead_v1_user_manual_for_help_files/image016.png /srv/shiny-server/www/Sig2Lead_v1_user_manual_for_help_files/
COPY ./app/www/Sig2Lead_v1_user_manual_for_help_files/image017.jpg /srv/shiny-server/www/Sig2Lead_v1_user_manual_for_help_files/

##########################################################################################################





#COPY ./app/files/sample2.txt /srv/shiny-server/files/
COPY ./app/files/LINCSCompounds.csv /srv/shiny-server/files/
COPY ./app/files/lincs_fps.Rdata /srv/shiny-server/files/
COPY ./app/files/minSim_apfp_RObjects.Rdata /srv/shiny-server/files/
COPY ./app/ui.R /srv/shiny-server/
COPY ./app/server.R /srv/shiny-server/
COPY ./app/lib /srv/shiny-server/lib
COPY ./app/similarity_search /srv/shiny-server/similarity_search
#COPY ./app/sample2.txt /srv/shiny-server/
#COPY ./app/smiles_test.txt /srv/shiny-server/


RUN chmod -R +rx /srv/shiny-server/ 

# EXPOSE 3838 
# CMD ["/usr/bin/shiny-server.sh"]


  

