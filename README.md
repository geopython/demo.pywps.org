# demo.pywps.org
demo.pywps.org setup

```bash
BASEDIR=/path/to/dir
mkdir $BASEDIR
cd $BASEDIR
git clone https://github.com/geopython/demo.pywps.org.git .
virtualenv $BASEDIR
. bin/$BASEDIR  # yes, that's a period
git clone https://github.com/geopython/demo.pywps.org.git .
# install PyWPS source
git clone https://github.com/geopython/pywps.git src/pywps && cd $_
python setup.py build
python setup.py install
# update server.home, server.url and repository.database in PyWPS/cite/cite.cfg
# setup www
vi etc/apache2/demo.pywps.org
# update DEMO_PYWPS_ORG_SECRET_KEY value with GitHub Webhook secret key
sudo ln -s etc/apache2/demo.pywps.org /etc/apache2/sites-available/
sudo a2ensite demo.pywps.org
sudo /usr/sbin/apache2ctl graceful
```
