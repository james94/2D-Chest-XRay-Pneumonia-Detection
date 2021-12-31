# James Guzman (Medel)
# Jupyter Notebook Py Docker Container
FROM jupyter/tensorflow-notebook:latest

WORKDIR /pneumoniaDetection

# add contents of pneumoniaDetection app to working dir
COPY . ./pneumoniaDetection/

# start jupyter notebook
CMD ["jupyter", "notebook"]
