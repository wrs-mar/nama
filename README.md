#Descompactar o arquivo 'upload.zip' em qualquer diretório de uma distro Linux baseda em Debian. Ubuntu é um exemplo.

# Instalar python 3.8

sudo apt update
sudo apt -y upgrade

# Instalar pip3

apt install python3-pip

# Instalar as bibliotecas 

pip3 install pandas
pip3 install numpy
pip3 install elasticsearch

# Instalar elasticsearch
curl -fsSL https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-7.x.list
sudo apt update
apt install elasticsearch

# Inicie o serviço do elasticsearch

systemctl start elasticsearch

# Acesse o diretório  descompactado 'upload' e execute o arquivo upload.py, os processos de: carregamento, análise, transformação, validação do tipo de dado e gravação no banco
# serão executados. O arquivo 'upload.py' é aberto, logo disponível para análise.


Execute o comando no terminal para visualizar dos dados gravados no banco de dados.

curl -XGET 'http://localhost:9200/dados/_search?pretty'
