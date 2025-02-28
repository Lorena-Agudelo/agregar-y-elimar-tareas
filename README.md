# agregar-y-elimar-tareas

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lista de Tareas</title>
    <script src="script.js" defer></script>
    <style>
    h2 {
        color: #2c3e50;}

    body {
            font-family: 'Arial', sans-serif;
            background-color: #f0f8ff;
            text-align: center;
        }


    </style>
</head>
<body>
    <h2>Lista de Tareas</h2>
    
    <input type="text" id="tarea" placeholder="Escribe una tarea">
    <button id="agregar">Agregar</button>
    <ul id="lista"></ul>

</body>
</html>
 <script>
document.addEventListener("DOMContentLoaded", () => {
    const inputTarea = document.querySelector("input");
    const botonAgregar = document.querySelector("button");
    const listaTareas = document.querySelector("ul");

    botonAgregar.addEventListener("click", () => {
        const textoTarea = inputTarea.value.trim();
        if (textoTarea !== "") {
            const li = document.createElement("li");
            li.textContent = textoTarea;
            
            const botonEliminar = document.createElement("button");
            botonEliminar.textContent = "Eliminar";
            botonEliminar.addEventListener("click", () => {
                listaTareas.removeChild(li);
            });

            li.appendChild(botonEliminar);
            listaTareas.appendChild(li);
            inputTarea.value = "";
            inputTarea.focus();
        }
    });
});
 </script>
