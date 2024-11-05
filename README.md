# Caldera Service

Recreates a service that is used for the startup of newer Fortnite builds.


## Tutorial

-> Open config.json and change the value to the version you want to start

-> Start the install_packages.bat and then the start.bat

## For login

-> You need to use the FortniteLauncher.exe and with that also the Anti Cheat 😔

-> If you use fiddler you can use this script :

    import Fiddler;
    
    class Handlers
    {
        static function OnBeforeRequest(oSession: Session) {
    
            if (oSession.PathAndQuery.Contains("/caldera/api/v1/launcher/racp"))
            {
                if (oSession.HTTPMethodIs("CONNECT"))
                {
                    oSession["x-replywithtunnel"] = "ServerTunnel";
                    return;
                }
                oSession.fullUrl = "http://127.0.0.1:5000" + oSession.PathAndQuery
            }
            if (oSession.hostname.Contains("epicgames"))
            {
                if (oSession.HTTPMethodIs("CONNECT"))
                {
                    oSession["x-replywithtunnel"] = "ServerTunnel";
                    return;
                }
                oSession.fullUrl = "http://127.0.0.1:3551" + oSession.PathAndQuery
            }
        }
    }
	

## Tested versions: 

-> Right now the only tested version is 27.11, if you test version please message me if it worked or not.

### TO EPIC, PLEASE DONT USE ME, YOU CAN MESSAGE ME AND I WILL INSTANTLY TAKE IT DOWN

### I AM NOT AFFILIATED WITH EPIC GAMES OR FORTNITE IN ANY WAY
