#DataViva
A Collaborative Planning Tool.
[dataviva.info](http://www.dataviva.info)

#Support

**DataViva** will run on all modern browsers so long as they have Javascript turned on and full support for SVG graphics. This includes the latest versions of Firefox, Chrome (Chromium), Safari (WebKit), Opera and IE.

Note: Internet Explorer versions 8 and below will not work as they do not have SVG support built in.

#Installation

**DataViva** is a web platform built using Flask, an open source Python library for interacting with HTTP. this installation guide is written assuming a Linux or Linux-like environment. The following software is required to be installed locally in order to get DataViva running:

*   Python
*   MySQL
*   Redis (at least version 2.8.6)

1.	Clone from github (this will create dataviva folder in the current directory)

        git clone https://github.com/alexandersimoes/dataviva.git
2.	[optional] Create a virtual environment. We suggest installing [virtualenv](https://pypi.python.org/pypi/virtualenv) with [virtualenvwrapper](http://virtualenvwrapper.readthedocs.org/en/latest/) especially if the machine you are using is used for many other web projects. This allows python libraries to be installed easily and specifically on a per proeject basis.

	Once this is complete, run the following to initialize your dataviva environment.


        mkvirtualenv dataviva
        workon dataviva
3.	Install the required Python libraries

        pip install -r requirements.txt
4.	Create a MySQL database and import the latest dump from [dataviva.info/static/db/](http://dataviva.info/static/db/)

        bzip2 < dataviva_xxxx-xx-xx.sql.bz2 | mysql -u USERNAME -p -h localhost DB_NAME
5.	Set the following environment variables

	**(if using virtualenv)** add the following to to the bottom of your virtualenv activate file (virtualenv_root/bin/activate).
	
        export DATAVIVA_SECRET_KEY=my-super-secret-k3y
        export DATAVIVA_DB_NAME=dataviva
        export DATAVIVA_DB_USER=root
        export DATAVIVA_DB_PW=my-pw
        * export DATAVIVA_ACCOUNTS=True
        
        * only necessary if you want to enable user accounts
6. Run the site locally!

        python run.py runserver