sudo add-apt-repository ppa:saiarcot895/chromium-beta &&
sudo apt remove chromium-browser &&
sudo snap remove chromium &&
sudo apt-get update &&
sudo apt install chromium-browser &&
sudo apt install chromium-chromedriver &&
sudo cp /usr/lib/chromium-browser/chromedriver /usr/bin

=== Evitando retornar à versão padrão do Chromium ===

Às vezes, este PPA não é atualizado dentro de alguns dias de um lançamento e, em alguns casos, a versão do Chromium nos repositórios padrão do Ubuntu pode ser mais recente do que a versão fornecida pelo PPA. Se você quiser impedir que o apt atualize para a versão nos repositórios padrão do Ubuntu, adicione as três linhas a seguir em 

sudo nano /etc/apt/preferences.d/chromium

Package: *
Pin: release o=LP-PPA-saiarcot895-chromium-beta
Pin-Priority: 700

sudo tee /etc/apt/preferences.d/chromium > /dev/null << EOF
Package: *
Pin: release o=LP-PPA-saiarcot895-chromium-beta
Pin-Priority: 700
EOF
