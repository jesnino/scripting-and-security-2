# Resumen de las operaciones con Memoria Compartida en PHP
## PHP 
### URL: https://www.jesusninoc.com/2018/04/05/resumen-de-las-operaciones-con-memoria-compartida-en-php/
```PHP
<?php
   
// Crear un segmento de memoria compartida de 100 bytes con un identificador igual a 0xff3
$shm_id = shmop_open(0xff3, "c", 0644, 100);
if (!$shm_id) {
    echo "Couldn't create shared memory segment\n";
}

// Obtener tamaño del segmento de memoria compartida
$shm_size = shmop_size($shm_id);
echo "SHM Block Size: " . $shm_size . " has been created.\n";

// Escribir una cadena de prueba en la memoria compartida
$shm_bytes_written = shmop_write($shm_id, "Prueba en la memoria compartida", 0);

// Ahora vamos a leer la cadena de texto
$my_string = shmop_read($shm_id, 0, $shm_size);
if (!$my_string) {
    echo "Couldn't read from shared memory block\n";
}
echo "The data inside shared memory was: " . $my_string . "\n";

//Ahora vamos a eliminar y cerrar el segmento de memoria compartida
if (!shmop_delete($shm_id)) {
    echo "Couldn't mark shared memory block for deletion.";
}
shmop_close($shm_id);
   
?>

```
```Shell
./php mem.php

```
