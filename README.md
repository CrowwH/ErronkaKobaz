# Erronka Kobaz
<p>Errepositorio honetan, Kobaz enpresaren Web orrialdea eta haren kopia aurkituko duzu. Baita ere Odoo eta Odoo-ren datu basearen kopia.</p>
<br>
<p>Ondorengo dokumentuan azalduta egongo da nola lortu dugun gure Nginx eda Odoo zerbitzuak martxan jartzen eta nola jarri dezakezu zuk martxan zure ordenagailuan.</p>
<br>

# Nola sortu Nginx kontenedorea:

Lehenengo errepositorio bat eduki behar dugu eginda. Hau egin ondoren gure Visual Studio Codera edo PowerShell-era joango gara eta terminal bat irekiko dugu. Terminal honetan ondorengo komandoa jarri beharko duzu[^1]:

[^1]: Karpeta bat sortu eta karpeta hori ireki VS-en eta klonatu karpetan horretan errepositorioa <br><br>
> [!NOTE]
> Highlights information that users should take into account, even when skimming.

<code>git clone "errepositorioaren helbidea"</code>
<p>Hau egin ondoren gure errepositorioa klonatuta geldituko da guk esan diogun karpetan</p>
<p>Ondoren gure Nginx kontenedorea egingo dugu.Horretarako ondorengo komandoa jarri beharko duzu terminalean</p>
<code> docker run --name "Nahi Duzun Zerbitzari Izena" -v "Non egongo da gordeta zure weborrialdea":/usr/share/nginx/html -p 80:80 -d nginx </code>
<p>Komando horrekin lortuko duguna da gure Nginx kontenedora sortzea eta martxan jartzea.</p>


# 🛠️ Ireki eta exekutatu Web Gunea eta Odoo-a:
<p>Gure web gunea zure ordenagailuan izateko, ondorengo comando jarri beharko duzu zure terminalean edo PowerShell-en</p>
<p>Lehenengo zure ordenagailuan GIT,WSL eta Docker instalatuta eduki behar izango duzu.</p>
<p>Ondoren gure GitHub-eko "docker-compose.yml" artxiboa deskargatu egin behar duzu eta ondoren ondorengo comando exekutatu:</p>

**Docker Compose-a altxatzeko**:
- <code>docker compose up</code>
<p>Zer dauka kode Honek?</p>
<code>version: '3.1'
services:
  web:
    image: nginx
    volumes:
      - ./ErronkaKobaz/web:/usr/share/nginx/html
    ports:
      - "8080:80"
    environment:
      - NGINX_HOST=foobar.com
      - NGINX_PORT=80
  odoo-server:
    image: odoo:16.0
    depends_on:
      - mydb
    ports:
      - "8069:8069"
    environment:
    - HOST=mydb
    - USER=odoo
    - PASSWORD=myodoo
  mydb:
    image: postgres:15
    environment:
      - POSTGRES_DB=postgres
      - POSTGRES_PASSWORD=myodoo
      - POSTGRES_USER=odoo</code>
