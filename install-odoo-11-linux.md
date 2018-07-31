# Install Odoo 11

> [official documentation](https://www.odoo.com/documentation/11.0/setup/install.html#fetch-the-sources)

Contrary to previous versions, this documentation seems to be enough to install 
Odoo 11 on your machine.
I advise creating a separate directory _eleven-odoo_ with the odoo repository on branch 11
and other custom modules repositories.
It will be easier to switch from an Odoo9 project to another.

That being said, here is the list of commands I used:

```bash
mkvirtualenv -p $(which python3) odoo11
mkdir eleven-odoo
cd eleven-odoo
git clone https://github.com/odoo/odoo.git -b 11.0 --depth 1
cd odoo
sudo apt install build-essential python3-dev libxslt-dev libzip-dev libldap2-dev libsasl2-dev
pip install -r requirements.txt
createdb test-odoo11
./odoo-bin --addons-path=addons --db-filter=test-odoo11$
```
