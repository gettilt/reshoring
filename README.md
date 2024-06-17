<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# America
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
Nationalism is rising, border walls are being built, and tariff wars are increasing. Everyone is motivated to buy locally, forcing a rebuilding of domestic infrastructure and manufacturing. U.S. based companies, manufacturers, and builders benefit.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| CAT | Caterpillar Inc. is a leading manufacturer of construction and mining equipment, which will benefit from increased domestic infrastructure projects. | chat_gpt,claude,twitter,google |
| DE | Deere & Company produces agricultural machinery, which will see increased demand as local farming becomes more prominent. | chat_gpt,twitter |
| DHI | D.R. Horton, Inc. is a leading homebuilder that will benefit from increased domestic construction. | chat_gpt |
| F | Ford Motor Company, as a U.S.-based automaker, will benefit from a shift towards buying locally manufactured vehicles. | chat_gpt,google |
| FDX | FedEx Corporation will benefit from increased demand for domestic shipping and logistics services. | chat_gpt,claude |
| GM | General Motors Company will also benefit from increased demand for domestically produced cars. | chat_gpt,google |
| HD | The Home Depot, Inc. will see increased sales as more people buy locally sourced building materials and home improvement products. | chat_gpt,claude |
| LEN | Lennar Corporation, another major homebuilder, will also see gains from the rise in domestic construction projects. | chat_gpt |
| MAS | Masco Corporation manufactures home improvement and building products, benefiting from increased domestic construction and renovation. | chat_gpt |
| MLM | Martin Marietta Materials, Inc. is another key supplier of construction materials, benefiting from increased domestic projects. | chat_gpt,claude |
| MMM | 3M Company, a diversified manufacturer, will benefit from increased demand for locally produced industrial and consumer products. | chat_gpt,claude |
| NUE | Nucor Corporation is a major U.S. steel producer, benefiting from increased demand for domestic steel in construction and manufacturing. | chat_gpt,claude |
| SHW | Sherwin-Williams Company, a leading paint and coatings manufacturer, will benefit from increased construction and renovation activities. | chat_gpt |
| UNP | Union Pacific Corporation, another major U.S. railroad, will also see gains from increased domestic freight transportation. | chat_gpt,claude,twitter |
| UPS | United Parcel Service, Inc. will also see increased demand for domestic shipping and logistics. | chat_gpt,twitter |
| VMC | Vulcan Materials Company supplies construction aggregates, essential for building infrastructure. | chat_gpt,claude |
| WHR | Whirlpool Corporation, a major U.S. appliance manufacturer, will see increased demand for locally made products. | chat_gpt |
| X | United States Steel Corporation will benefit from tariffs on imported steel and increased domestic infrastructure projects. | chat_gpt,claude |
| AMZN | Amazon, with its strong domestic presence and extensive logistics network, may benefit from the growing trend of buying locally and the need for efficient domestic distribution. | claude |
| GE | GE, a diversified industrial company, may benefit from increased domestic manufacturing and infrastructure projects, particularly in the energy and transportation sectors. | claude,google |
| HON | Honeywell, a diversified technology and manufacturing company, could benefit from the growing demand for automation and connected solutions in domestic manufacturing facilities. | claude |
| J | Jacobs Engineering, a provider of technical and construction services, may see increased opportunities as domestic infrastructure and manufacturing projects expand. | claude |
| LMT | Lockheed Martin, a leading defense contractor, could benefit from rising nationalism and potential increases in defense spending to protect borders and domestic interests. | claude,twitter,google |
| ROK | Rockwell Automation, a provider of industrial automation solutions, could see increased demand as domestic manufacturers invest in modernizing their facilities. | claude |
| TER | Teradyne, a leading supplier of automated test equipment, may benefit from the expansion of domestic manufacturing and the need for quality control solutions. | claude |
| WMT | Walmart, the largest U.S. retailer, could benefit from the growing trend of buying locally as consumers focus on supporting domestic businesses and products. | claude,google |
| CMG |  | twitter |
| CNI |  | twitter |
| CP |  | twitter |
| RTX |  | twitter |
| WM |  | twitter |
| INTC |  | google |
| MSCI |  | google |
| TSM |  | google |
| VRRM |  | google |
| BRC |  | expert |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/reshoring/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/reshoring" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
