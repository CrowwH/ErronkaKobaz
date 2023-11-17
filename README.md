# Erronka Kobaz
<p>Errepositorio honetan, Kobaz enpresaren Web orrialdea eta haren kopia aurkituko duzu. Baita ere Odoo eta Odoo-ren datu basearen kopia.</p>
<br>
<p>Ondorengo dokumentuan azalduta egongo da nola lortu dugun gure Nginx eda Odoo zerbitzuak martxan jartzen eta nola jarri dezakezu zuk martxan zure ordenagailuan.</p>
<br>

# Nola sortu Nginx kontenedorea:

Lehenengo errepositorio bat eduki behar dugu eginda. Hau egin ondoren gure Visual Studio Codera edo PowerShell-era joango gara eta terminal bat irekiko dugu. Terminal honetan ondorengo komandoa jarri beharko duzu[^1]:

[^1]: Karpeta bat sortu eta karpeta hori ireki VS-en eta klonatu karpetan horretan errepositorioa <br><br>

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
