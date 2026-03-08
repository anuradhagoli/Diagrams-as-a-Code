# Diagrams
## Diagram as Code

Reference : [https://diagrams.mingrammer.com/](https://diagrams.mingrammer.com/docs/getting-started/installation) 

### Installation
diagrams requires Python 3.7 or higher, check your Python version first.
diagrams uses Graphviz to render the diagram, so you need to install Graphviz to use it.
macOS users using Homebrew can install Graphviz via brew install graphviz . Similarly, Windows users with Chocolatey installed can run choco install graphviz or use Winget via winget install Graphviz.Graphviz -i.

After installing Graphviz (or if you already have it), install diagrams:

### using pip (pip3)
`$ pip install diagrams`

### using pipenv
`$ pipenv install diagrams`

### using poetry
`$ poetry add diagrams`

### using uv
`$ uv tool install diagrams`

## Quick Start
# diagram.py
      from diagrams import Diagram
      from diagrams.aws.compute import EC2
      from diagrams.aws.database import RDS
      from diagrams.aws.network import ELB
      
      with Diagram("Web Service", show=False):
          ELB("lb") >> EC2("web") >> RDS("userdb")
    
To generate the diagram, run:
`$ python diagram.py`

This generates the diagram below:

web service diagram 
<img src="web_service.png"/>

It will be saved as web_service.png in your working directory.

CLI
With the diagrams CLI you can process one or more diagram files at once.

`$ diagrams diagram1.py diagram2.py`
