<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">

    <!-- Cargamos CSS -->
    <link rel="stylesheet" href="estilo.css">

    <!-- Nombre de la pestaña -->
    <title>Mi Pagina Web</title>
</head>

<body>
    <header id="home" class="cabeceraPagina">
        <h1><b>Mi Pagina Web</b></h1>
    </header>
    <nav>
        <ul>
            <li>
                <a href="#home">Home</a>
            </li>
            <li>
                <a href="#sobreNosotros">Sobre Nosotros</a>
            </li>
            <li>
                <a href="#empleados">Empleados</a>
            </li>
            <li>
                <a href="#noticias">Noticias</a>
            </li>
        </ul>
    </nav>
    <div class="contenidoPrincipal">
        <div class="sobreNosotros" id="sobreNosotros">
            <h3>Sobre Nosotros</h3>
            <p>
                Lorem ipsum dolor, sit amet consectetur adipisicing <strong>elit</strong>. Dolore minus impedit,
                accusamus enim fuga eius deserunt illo cumque eaque et temporibus commodi repudiandae
                natus veritatis quo. Laudantium, sunt praesentium?
                Lorem ipsum dolor, sit amet consectetur adipisicing elit. Dolore minus impedit,accusamus
                enim fuga eius deserunt illo cumque eaque et temporibus commodi repudiandae natus veritatis quo.
                Laudantium, sunt praesentium? Lorem ipsum dolor, sit amet consectetur adipisicing elit. Dolore
                minus impedit, accusamus enim fuga eius deserunt illo cumque eaque et temporibus commodi repudiandae
                natus veritatis quo. Laudantium, sunt praesentium?
                Lorem ipsum dolor, sit amet consectetur adipisicing <u>elit</u>. Dolore minus impedit,accusamus
                enim fuga eius deserunt illo cumque eaque et temporibus commodi repudiandae natus veritatis quo.
                Laudantium, sunt praesentium? Lorem ipsum dolor, sit amet consectetur adipisicing elit. Dolore
                minus impedit, accusamus enim fuga eius deserunt illo cumque eaque et temporibus commodi repudiandae
                natus veritatis quo. Laudantium, sunt praesentium?
                Laudantium, sunt praesentium? Lorem ipsum dolor, sit amet consectetur adipisicing elit. Dolore
                minus impedit, accusamus enim fuga eius deserunt illo cumque eaque et temporibus commodi repudiandae
            </p>
            <img src="imagenes/SobreNosotros.jpg">
        </div>
        <br>
		<br>
		<br>
		<br>
        <div class="empleados" id="empleados">
			<br>
			<br>
			<br>
            <h3>Nuestros Empleados</h3>
            <table class="tablaEmpleados">
                <tr class="cabecera">
                    <th>
                        Nombre
                    </th>
                    <th>
                        Edad
                    </th>
                    <th>
                        NickName
                    </th>
                    <th>
                        Salario
                    </th>
                    <th>
                        Puesto
                    </th>
                </tr>
                <tr class="tablaPersona">
                    <th>
                        Pedro Lopez Ruiz
                    </th>
                    <th>
                        32
                    </th>
                    <th>
                        pedroloru
                    </th>
                    <th>
                        5600
                    </th>
                    <th>
                        Puesto 1
                    </th>
                </tr>
                <tr class="tablaPersona">
                    <th>
                        Jose Lopez Ruiz
                    </th>
                    <th>
                        32
                    </th>
                    <th>
                        joselopez
                    </th>
                    <th>
                        5600
                    </th>
                    <th>
                        Puesto 3
                    </th>
                </tr>
                <tr class="tablaPersona">
                    <th>
                        Ana Lopez Ruiz
                    </th>
                    <th>
                        21
                    </th>
                    <th>
                        anaPuesto
                    </th>
                    <th>
                        1222
                    </th>
                    <th>
                        Puesto 4
                    </th>
                </tr>
                <tr class="tablaPersona">
                    <th>
                        Sara Milla Ruiz
                    </th>
                    <th>
                        34
                    </th>
                    <th>
                        saraPuesto
                    </th>
                    <th>
                        4000
                    </th>
                    <th>
                        Puesto 5
                    </th>
                </tr>
            </table>
        </div>
        <h3>Nuestras Opiniones</h3>
        <div class="nuestrasOpiniones" id="nuestrasOpiniones">
            <div class="item">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Dolore minus impedit,
                accusamus enim fuga eius deserunt illo cumque eaque et temporibus commodi repudiandae
                natus veritatis quo. Laudantium, sunt praesentium?
            </div>
            <div class="item">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Dolore minus impedit,
                accusamus enim fuga eius deserunt illo cumque eaque et temporibus commodi repudiandae
                natus veritatis quo. Laudantium, sunt praesentium?
            </div>
            <div class="item">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Dolore minus impedit,
                accusamus enim fuga eius deserunt illo cumque eaque et temporibus commodi repudiandae
                natus veritatis quo. Laudantium, sunt praesentium?
            </div>
            <div class="item">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Dolore minus impedit,
                accusamus enim fuga eius deserunt illo cumque eaque et temporibus commodi repudiandae
                natus veritatis quo. Laudantium, sunt praesentium?
            </div>
        </div>
    </div>

    <div class="noticias" id="noticias">
        <h2>Subscribite a nuestras noticias</h2>
        <form action="/action" method="get">
			<br>
			<br>
            <input type="text" >
        </form>
    </div>
    <footer class="footer">
        Pagina Web @ 2022
    </footer>
</body>

</html>
