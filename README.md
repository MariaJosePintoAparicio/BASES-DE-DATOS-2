# TRABAJO BASES DE DATOS 2



### Consultas sobre una tabla

1. Lista el primer apellido de todos los empleados.

   ```sql
   SELECT apellido1 FROM empleado;
   +-----------+
   | apellido1 |
   +-----------+
   | Rivero    |
   | Salas     |
   | Rubio     |
   | Suárez    |
   | Loyola    |
   | Santana   |
   | Ruiz      |
   | Ruiz      |
   | Gómez     |
   | Flores    |
   | Herrera   |
   | Salas     |
   | Sáez      |
   +-----------+
   
   
   ```

   

2. Lista el primer apellido de los empleados eliminando los apellidos que estén
   repetidos.

   ```sql
   SELECT DISTINCT apellido1 FROM empleado;
   +-----------+
   | apellido1 |
   +-----------+
   | Rivero    |
   | Salas     |
   | Rubio     |
   | Suárez    |
   | Loyola    |
   | Santana   |
   | Ruiz      |
   | Gómez     |
   | Flores    |
   | Herrera   |
   | Sáez      |
   +-----------+
   
   ```

   

3. Lista todas las columnas de la tabla empleado.

   ```sql
   SELECT codigo , nombre , nif, apellido1 , apellido2 , codigo_departamento FROM empleado;
   +--------+--------------+-----------+-----------+-----------+---------------------+
   | codigo | nombre       | nif       | apellido1 | apellido2 | codigo_departamento |
   +--------+--------------+-----------+-----------+-----------+---------------------+
   |      1 | Aarón        | 32481596F | Rivero    | Gómez     |                   1 |
   |      2 | Adela        | Y5575632D | Salas     | Díaz      |                   2 |
   |      3 | Adolfo       | R6970642B | Rubio     | Flores    |                   3 |
   |      4 | Adrián       | 77705545E | Suárez    | NULL      |                   4 |
   |      5 | Marcos       | 17087203C | Loyola    | Méndez    |                   5 |
   |      6 | María        | 38382980M | Santana   | Moreno    |                   1 |
   |      7 | Pilar        | 80576669X | Ruiz      | NULL      |                   2 |
   |      8 | Pepe         | 71651431Z | Ruiz      | Santana   |                   3 |
   |      9 | Juan         | 56399183D | Gómez     | López     |                   2 |
   |     10 | Diego        | 46384486H | Flores    | Salas     |                   5 |
   |     11 | Marta        | 67389283A | Herrera   | Gil       |                   1 |
   |     12 | Irene        | 41234836R | Salas     | Flores    |                NULL |
   |     13 | Juan Antonio | 82635162B | Sáez      | Guerrero  |                NULL |
   +--------+--------------+-----------+-----------+-----------+---------------------+
   
   ```

   

4. Lista el nombre y los apellidos de todos los empleados.

   ```sql
   SELECT nombre , apellido1 , apellido2 FROM empleado;
   +--------------+-----------+-----------+
   | nombre       | apellido1 | apellido2 |
   +--------------+-----------+-----------+
   | Aarón        | Rivero    | Gómez     |
   | Adela        | Salas     | Díaz      |
   | Adolfo       | Rubio     | Flores    |
   | Adrián       | Suárez    | NULL      |
   | Marcos       | Loyola    | Méndez    |
   | María        | Santana   | Moreno    |
   | Pilar        | Ruiz      | NULL      |
   | Pepe         | Ruiz      | Santana   |
   | Juan         | Gómez     | López     |
   | Diego        | Flores    | Salas     |
   | Marta        | Herrera   | Gil       |
   | Irene        | Salas     | Flores    |
   | Juan Antonio | Sáez      | Guerrero  |
   +--------------+-----------+-----------+
   
   ```

   

5. Lista el identificador de los departamentos de los empleados que aparecen
   en la tabla empleado.

   ```sql
   SELECT codigo_departamento FROM empleado WHERE codigo_departamento IS NOT NULL; 
   +---------------------+
   | codigo_departamento |
   +---------------------+
   |                   1 |
   |                   1 |
   |                   1 |
   |                   2 |
   |                   2 |
   |                   2 |
   |                   3 |
   |                   3 |
   |                   4 |
   |                   5 |
   |                   5 |
   +---------------------+
   
   ```

   

6. Lista el identificador de los departamentos de los empleados que aparecen
   en la tabla empleado, eliminando los identificadores que aparecen repetidos.

   ```sql
   SELECT DISTINCT codigo_departamento FROM empleado WHERE codigo_departamento IS NOT NULL; 
   +---------------------+
   | codigo_departamento |
   +---------------------+
   |                   1 |
   |                   2 |
   |                   3 |
   |                   4 |
   |                   5 |
   +---------------------+
   ```

   

7. Lista el nombre y apellidos de los empleados en una única columna.

   ```sql
   SELECT CONCAT (nombre, ' ', apellido1 , ' ',apellido2  ) as NOMBRE_COMPLETO FROM empleado;
   +-----------------------------+
   | NOMBRE_COMPLETO             |
   +-----------------------------+
   | Aarón Rivero Gómez          |
   | Adela Salas Díaz            |
   | Adolfo Rubio Flores         |
   | NULL                        |
   | Marcos Loyola Méndez        |
   | María Santana Moreno        |
   | NULL                        |
   | Pepe Ruiz Santana           |
   | Juan Gómez López            |
   | Diego Flores Salas          |
   | Marta Herrera Gil           |
   | Irene Salas Flores          |
   | Juan Antonio Sáez Guerrero  |
   +-----------------------------+
   ```

   

8. Lista el nombre y apellidos de los empleados en una única columna,
   convirtiendo todos los caracteres en mayúscula.

   ```sql
   SELECT  UPPER (CONCAT (nombre, ' ', apellido1 , ' ',apellido2  )) as NOMBRE_COMPLETO FROM empleado;
   +-----------------------------+
   | NOMBRE_COMPLETO             |
   +-----------------------------+
   | AARÓN RIVERO GÓMEZ          |
   | ADELA SALAS DÍAZ            |
   | ADOLFO RUBIO FLORES         |
   | NULL                        |
   | MARCOS LOYOLA MÉNDEZ        |
   | MARÍA SANTANA MORENO        |
   | NULL                        |
   | PEPE RUIZ SANTANA           |
   | JUAN GÓMEZ LÓPEZ            |
   | DIEGO FLORES SALAS          |
   | MARTA HERRERA GIL           |
   | IRENE SALAS FLORES          |
   | JUAN ANTONIO SÁEZ GUERRERO  |
   +-----------------------------+
   
   ```

   

9. Lista el nombre y apellidos de los empleados en una única columna,
   convirtiendo todos los caracteres en minúscula.

   ```sql
   SELECT  LOWER (CONCAT (nombre, ' ', apellido1 , ' ',apellido2  )) as NOMBRE_COMPLETO FROM empleado;
   +-----------------------------+
   | NOMBRE_COMPLETO             |
   +-----------------------------+
   | aarón rivero gómez          |
   | adela salas díaz            |
   | adolfo rubio flores         |
   | NULL                        |
   | marcos loyola méndez        |
   | maría santana moreno        |
   | NULL                        |
   | pepe ruiz santana           |
   | juan gómez lópez            |
   | diego flores salas          |
   | marta herrera gil           |
   | irene salas flores          |
   | juan antonio sáez guerrero  |
   +-----------------------------+
   ```

   

10. Lista el identificador de los empleados junto al nif, pero el nif deberá
    aparecer en dos columnas, una mostrará únicamente los dígitos del nif y la
    otra la letra.
    SELECT e.codigo, SUBSTRING(nif, 1, LENGTH(nif) - 1) AS DIGITOS, RIGHT(nif, 1) AS LETRAS
    FROM empleado AS e;
        +--------+----------+--------+
        | codigo | DIGITOS  | LETRAS |
        +--------+----------+--------+
        |      1 | 32481596 | F      |
        |      2 | Y5575632 | D      |
        |      3 | R6970642 | B      |
        |      4 | 77705545 | E      |
        |      5 | 17087203 | C      |
        |      6 | 38382980 | M      |
        |      7 | 80576669 | X      |
        |      8 | 71651431 | Z      |
        |      9 | 56399183 | D      |
        |     10 | 46384486 | H      |
        |     11 | 67389283 | A      |
        |     12 | 41234836 | R      |
        |     13 | 82635162 | B      |
        +--------+----------+--------+
        13 rows in set (0,00 sec)

    

11. Lista el nombre de cada departamento y el valor del presupuesto actual del
    que dispone. Para calcular este dato tendrá que restar al valor del
    presupuesto inicial (columna presupuesto) los gastos que se han generado
    (columna gastos). Tenga en cuenta que en algunos casos pueden existir
    valores negativos. Utilice un alias apropiado para la nueva columna columna
    que está calculando.

    ```sql
    SELECT nombre ,(presupuesto - gastos) AS presupuesto_actual FROM departamento;
    +------------------+--------------------+
    | nombre           | presupuesto_actual |
    +------------------+--------------------+
    | Desarrollo       |             114000 |
    | Sistemas         |             129000 |
    | Recursos Humanos |             255000 |
    | Contabilidad     |             107000 |
    | I+D              |              -5000 |
    | Proyectos        |                  0 |
    | Publicidad       |              -1000 |
    +------------------+--------------------+
    ```

    

12. Lista el nombre de los departamentos y el valor del presupuesto actual
    ordenado de forma ascendente.

    ```SQL
    SELECT nombre ,(presupuesto - gastos) AS presupuesto_actual FROM departamento ORDER BY presupuesto_actual ASC;
    +------------------+--------------------+
    | nombre           | presupuesto_actual |
    +------------------+--------------------+
    | I+D              |              -5000 |
    | Publicidad       |              -1000 |
    | Proyectos        |                  0 |
    | Contabilidad     |             107000 |
    | Desarrollo       |             114000 |
    | Sistemas         |             129000 |
    | Recursos Humanos |             255000 |
    +------------------+--------------------+
    ```

    

13. Lista el nombre de todos los departamentos ordenados de forma
    ascendente.

    ```SQL
    SELECT nombre FROM departamento ORDER BY nombre ASC;
    +------------------+
    | nombre           |
    +------------------+
    | Contabilidad     |
    | Desarrollo       |
    | I+D              |
    | Proyectos        |
    | Publicidad       |
    | Recursos Humanos |
    | Sistemas         |
    +------------------+
    ```

    

14. Lista el nombre de todos los departamentos ordenados de forma
    descendente.

    ```SQL
    SELECT nombre FROM departamento ORDER BY nombre DESC;
    +------------------+
    | nombre           |
    +------------------+
    | Sistemas         |
    | Recursos Humanos |
    | Publicidad       |
    | Proyectos        |
    | I+D              |
    | Desarrollo       |
    | Contabilidad     |
    +------------------+
    ```

    

15. Lista los apellidos y el nombre de todos los empleados, ordenados de forma
    alfabética tendiendo en cuenta en primer lugar sus apellidos y luego su
    nombre.

    ```SQL
    SELECT apelido1 , apellido2 , nombre FROM empleado ORDER BY apellido1 , apellido2 , nombre ASC;
    +-----------+-----------+--------------+
    | apelLido1 | apellido2 | nombre       |
    +-----------+-----------+--------------+
    | Flores    | Salas     | Diego        |
    | Gómez     | López     | Juan         |
    | Herrera   | Gil       | Marta        |
    | Loyola    | Méndez    | Marcos       |
    | Rivero    | Gómez     | Aarón        |
    | Rubio     | Flores    | Adolfo       |
    | Ruiz      | NULL      | Pilar        |
    | Ruiz      | Santana   | Pepe         |
    | Sáez      | Guerrero  | Juan Antonio |
    | Salas     | Díaz      | Adela        |
    | Salas     | Flores    | Irene        |
    | Santana   | Moreno    | María        |
    | Suárez    | NULL      | Adrián       |
    +-----------+-----------+--------------+
    ```

    

16. Devuelve una lista con el nombre y el presupuesto, de los 3 departamentos
    que tienen mayor presupuesto.

    ```sql
    SELECT nombre , presupuesto FROM departamento ORDER BY presupuesto DESC LIMIT 3;
    +------------------+-------------+
    | nombre           | presupuesto |
    +------------------+-------------+
    | I+D              |      375000 |
    | Recursos Humanos |      280000 |
    | Sistemas         |      150000 |
    +------------------+-------------+
    ```

    

17. Devuelve una lista con el nombre y el presupuesto, de los 3 departamentos
    que tienen menor presupuesto.

    ```sql
    SELECT nombre , presupuesto FROM departamento ORDER BY presupuesto ASC LIMIT 3;
    +--------------+-------------+
    | nombre       | presupuesto |
    +--------------+-------------+
    | Proyectos    |           0 |
    | Publicidad   |           0 |
    | Contabilidad |      110000 |
    +--------------+-------------+
    ```

    

18. Devuelve una lista con el nombre y el gasto, de los 2 departamentos que
    tienen mayor gasto.

    ```sql
    SELECT nombre , gasto FROM departamento ORDER BY gasto DESC LIMIT 2;
    +------------------+--------+
    | nombre           | gastos |
    +------------------+--------+
    | I+D              | 380000 |
    | Recursos Humanos |  25000 |
    +------------------+--------+
    ```

    

19. Devuelve una lista con el nombre y el gasto, de los 2 departamentos que
    tienen menor gasto.

    ```sql
    SELECT nombre , gasto FROM departamento ORDER BY gasto ASC LIMIT 2;
    +------------+--------+
    | nombre     | gastos |
    +------------+--------+
    | Proyectos  |      0 |
    | Publicidad |   1000 |
    +------------+--------+
    ```

    

20. Devuelve una lista con 5 filas a partir de la tercera fila de la tabla empleado. La
    tercera fila se debe incluir en la respuesta. La respuesta debe incluir todas las
    columnas de la tabla empleado.

    ```sql
    SELECT codigo , nombre , nif, apellido1 , apellido2 , codigo_departamento  FROM empleado LIMIT 5 OFFSET 2;
    +--------+---------+-----------+-----------+-----------+---------------------+
    | codigo | nombre  | nif       | apellido1 | apellido2 | codigo_departamento |
    +--------+---------+-----------+-----------+-----------+---------------------+
    |      3 | Adolfo  | R6970642B | Rubio     | Flores    |                   3 |
    |      4 | Adrián  | 77705545E | Suárez    | NULL      |                   4 |
    |      5 | Marcos  | 17087203C | Loyola    | Méndez    |                   5 |
    |      6 | María   | 38382980M | Santana   | Moreno    |                   1 |
    |      7 | Pilar   | 80576669X | Ruiz      | NULL      |                   2 |
    +--------+---------+-----------+-----------+-----------+---------------------+
    ```

    

21. Devuelve una lista con el nombre de los departamentos y el presupuesto, de
    aquellos que tienen un presupuesto mayor o igual a 150000 euros.

    ```sql
    SELECT nombre, presupuesto FROM departamento WHERE presupuesto >= 150000;
    +------------------+-------------+
    | nombre           | presupuesto |
    +------------------+-------------+
    | Sistemas         |      150000 |
    | Recursos Humanos |      280000 |
    | I+D              |      375000 |
    +------------------+-------------+
    ```

    

22. Devuelve una lista con el nombre de los departamentos y el gasto, de
    aquellos que tienen menos de 5000 euros de gastos.

    ```sql
    SELECT nombre, gastos FROM departamento WHERE gastos >= 5000;
    +------------------+--------+
    | nombre           | gastos |
    +------------------+--------+
    | Desarrollo       |   6000 |
    | Sistemas         |  21000 |
    | Recursos Humanos |  25000 |
    | I+D              | 380000 |
    +------------------+--------+
    ```

    

23. Devuelve una lista con el nombre de los departamentos y el presupuesto, de
    aquellos que tienen un presupuesto entre 100000 y 200000 euros. Sin
    utilizar el operador BETWEEN.

    ```SQL
    SELECT nombre, presupuesto FROM departamento WHERE presupuesto > 100000 AND presupuesto < 200000;
    +--------------+-------------+
    | nombre       | presupuesto |
    +--------------+-------------+
    | Desarrollo   |      120000 |
    | Sistemas     |      150000 |
    | Contabilidad |      110000 |
    +--------------+-------------+
    ```

    

24. Devuelve una lista con el nombre de los departamentos que no tienen un
    presupuesto entre 100000 y 200000 euros. Sin utilizar el operador BETWEEN.

    ```SQL
    SELECT nombre, presupuesto FROM departamento WHERE presupuesto < 100000 OR presupuesto > 200000;
    +------------------+-------------+
    | nombre           | presupuesto |
    +------------------+-------------+
    | Recursos Humanos |      280000 |
    | I+D              |      375000 |
    | Proyectos        |           0 |
    | Publicidad       |           0 |
    +------------------+-------------+
    ```

    

25. Devuelve una lista con el nombre de los departamentos que tienen un
    presupuesto entre 100000 y 200000 euros. Utilizando el operador BETWEEN.

    ```SQL
    SELECT nombre, presupuesto FROM departamento WHERE presupuesto BETWEEN 100000 AND 200000;
    +--------------+-------------+
    | nombre       | presupuesto |
    +--------------+-------------+
    | Desarrollo   |      120000 |
    | Sistemas     |      150000 |
    | Contabilidad |      110000 |
    +--------------+-------------+
    ```

    

26. Devuelve una lista con el nombre de los departamentos que no tienen un
    presupuesto entre 100000 y 200000 euros. Utilizando el operador BETWEEN.

    ```SQL
    SELECT nombre, presupuesto FROM departamento WHERE presupuesto NOT BETWEEN 100000 AND 200000;
    +------------------+-------------+
    | nombre           | presupuesto |
    +------------------+-------------+
    | Recursos Humanos |      280000 |
    | I+D              |      375000 |
    | Proyectos        |           0 |
    | Publicidad       |           0 |
    +------------------+-------------+
    ```

    

27. Devuelve una lista con el nombre de los departamentos, gastos y
    presupuesto, de aquellos departamentos donde los gastos sean mayores
    que el presupuesto del que disponen.

    ```sql
    SELECT nombre, gastos, presupuesto FROM departamento WHERE gastos > presupuesto;
    +------------+--------+-------------+
    | nombre     | gastos | presupuesto |
    +------------+--------+-------------+
    | I+D        | 380000 |      375000 |
    | Publicidad |   1000 |           0 |
    +------------+--------+-------------+
    ```

    

28. Devuelve una lista con el nombre de los departamentos, gastos y
    presupuesto, de aquellos departamentos donde los gastos sean menores
    que el presupuesto del que disponen.

    ```sql
    SELECT nombre, gastos, presupuesto FROM departamento WHERE gastos < presupuesto;
    +------------------+--------+-------------+
    | nombre           | gastos | presupuesto |
    +------------------+--------+-------------+
    | Desarrollo       |   6000 |      120000 |
    | Sistemas         |  21000 |      150000 |
    | Recursos Humanos |  25000 |      280000 |
    | Contabilidad     |   3000 |      110000 |
    +------------------+--------+-------------+
    ```

    

29. Devuelve una lista con el nombre de los departamentos, gastos y
    presupuesto, de aquellos departamentos donde los gastos sean iguales al
    presupuesto del que disponen.

    ```sql
    SELECT nombre, gastos, presupuesto FROM departamento WHERE gastos = presupuesto;
    +-----------+--------+-------------+
    | nombre    | gastos | presupuesto |
    +-----------+--------+-------------+
    | Proyectos |      0 |           0 |
    +-----------+--------+-------------+
    ```

    

30. Lista todos los datos de los empleados cuyo segundo apellido sea NULL.

    ```sql
    SELECT id, nombre, nif, apellido1, apellido2, id_departamento 
    FROM empleado 
    WHERE apellido2 IS NULL;
    +----+---------+-----------+-----------+-----------+-----------------+
    | id | nombre  | nif       | apellido1 | apellido2 | id_departamento |
    +----+---------+-----------+-----------+-----------+-----------------+
    |  4 | Adrián  | 77705545E | Suárez    | NULL      |               4 |
    |  7 | Pilar   | 80576669X | Ruiz      | NULL      |               2 |
    +----+---------+-----------+-----------+-----------+-----------------+
    ```

31. Lista todos los datos de los empleados cuyo segundo apellido no sea NULL.

    ```sql
    SELECT id, nombre, nif, apellido1, apellido2, id_departamento 
    FROM empleado
    WHERE apellido2 IS NOT NULL;
    +----+--------------+-----------+-----------+-----------+-----------------+
    | id | nombre       | nif       | apellido1 | apellido2 | id_departamento |
    +----+--------------+-----------+-----------+-----------+-----------------+
    |  1 | Aarón        | 32481596F | Rivero    | Gómez     |               1 |
    |  2 | Adela        | Y5575632D | Salas     | Díaz      |               2 |
    |  3 | Adolfo       | R6970642B | Rubio     | Flores    |               3 |
    |  5 | Marcos       | 17087203C | Loyola    | Méndez    |               5 |
    |  6 | María        | 38382980M | Santana   | Moreno    |               1 |
    |  8 | Pepe         | 71651431Z | Ruiz      | Santana   |               3 |
    |  9 | Juan         | 56399183D | Gómez     | López     |               2 |
    | 10 | Diego        | 46384486H | Flores    | Salas     |               5 |
    | 11 | Marta        | 67389283A | Herrera   | Gil       |               1 |
    | 12 | Irene        | 41234836R | Salas     | Flores    |            NULL |
    | 13 | Juan Antonio | 82635162B | Sáez      | Guerrero  |            NULL |
    +----+--------------+-----------+-----------+-----------+-----------------+
    ```

    

32. Lista todos los datos de los empleados cuyo segundo apellido sea López.

    ```sql
    SELECT id, nombre, nif, apellido1, apellido2, id_departamento 
    FROM   empleado
    WHERE  apellido2 = 'lopez';
    +----+--------+-----------+-----------+-----------+-----------------+
    | id | nombre | nif       | apellido1 | apellido2 | id_departamento |
    +----+--------+-----------+-----------+-----------+-----------------+
    |  9 | Juan   | 56399183D | Gómez     | López     |               2 |
    +----+--------+-----------+-----------+-----------+-----------------+
    ```

    

33. Lista todos los datos de los empleados cuyo segundo apellido
    sea Díaz o Moreno. Sin utilizar el operador IN.

    ```sql
    SELECT id, nombre, nif, apellido1, apellido2, id_departamento 
    FROM   empleado
    WHERE  apellido2 = 'Diaz' OR apellido2 = 'Moreno';
    +----+--------+-----------+-----------+-----------+-----------------+
    | id | nombre | nif       | apellido1 | apellido2 | id_departamento |
    +----+--------+-----------+-----------+-----------+-----------------+
    |  2 | Adela  | Y5575632D | Salas     | Díaz      |               2 |
    |  6 | María  | 38382980M | Santana   | Moreno    |               1 |
    +----+--------+-----------+-----------+-----------+-----------------+
    ```

34. Lista todos los datos de los empleados cuyo segundo apellido
    sea Díaz o Moreno. Utilizando el operador IN.

    ```sql
    SELECT id, nombre, nif, apellido1, apellido2, id_departamento 
    FROM   empleado
    WHERE  apellido2 IN ('Diaz' , 'Moreno');
    +----+--------+-----------+-----------+-----------+-----------------+
    | id | nombre | nif       | apellido1 | apellido2 | id_departamento |
    +----+--------+-----------+-----------+-----------+-----------------+
    |  2 | Adela  | Y5575632D | Salas     | Díaz      |               2 |
    |  6 | María  | 38382980M | Santana   | Moreno    |               1 |
    +----+--------+-----------+-----------+-----------+-----------------+
    
    ```

    

35. Lista los nombres, apellidos y nif de los empleados que trabajan en el
    departamento 3.

    ```sql
    SELECT nombre, apellido1, apellido2, nif
    FROM empleado
    WHERE id_departamento = 2;
    +--------+-----------+-----------+-----------+
    | nombre | apellido1 | apellido2 | nif       |
    +--------+-----------+-----------+-----------+
    | Adela  | Salas     | Díaz      | Y5575632D |
    | Pilar  | Ruiz      | NULL      | 80576669X |
    | Juan   | Gómez     | López     | 56399183D |
    +--------+-----------+-----------+-----------+
    ```

36. Lista los nombres, apellidos y nif de los empleados que trabajan en los
    departamentos 2, 4 o 5.

    ```SQL
    SELECT nombre , apellido1 , apellido2 , nif, id_departamento 
    FROM empleado 
    WHERE id_departamento IN (2,4,5);
    +---------+-----------+-----------+-----------+-----------------+
    | nombre  | apellido1 | apellido2 | nif       | id_departamento |
    +---------+-----------+-----------+-----------+-----------------+
    | Adela   | Salas     | Díaz      | Y5575632D |               2 |
    | Pilar   | Ruiz      | NULL      | 80576669X |               2 |
    | Juan    | Gómez     | López     | 56399183D |               2 |
    | Adrián  | Suárez    | NULL      | 77705545E |               4 |
    | Marcos  | Loyola    | Méndez    | 17087203C |               5 |
    | Diego   | Flores    | Salas     | 46384486H |               5 |
    +---------+-----------+-----------+-----------+-----------------+
    ```

    

### Consultas multitabla (Composición interna)

Resuelva todas las consultas utilizando la sintaxis de SQL1 y SQL2.

1. Devuelve un listado con los empleados y los datos de los departamentos
    donde trabaja cada uno.

  ```sql
  SELECT  e.id , e.nif , e.nombre, e.apellido1, e.apellido2 , e.id_departamento , d.id, d.nombre, d.presupuesto, d.gastos 
  FROM empleado AS e,departamento AS d
  WHERE e.id_departamento = d.id;
  
  
  +----+-----------+---------+-----------+-----------+-----------------+----+------------------+-------------+--------+
  | id | nif       | nombre  | apellido1 | apellido2 | id_departamento | id | nombre           | presupuesto | gastos |
  +----+-----------+---------+-----------+-----------+-----------------+----+------------------+-------------+--------+
  |  1 | 32481596F | Aarón   | Rivero    | Gómez     |               1 |  1 | Desarrollo       |      120000 |   6000 |
  |  6 | 38382980M | María   | Santana   | Moreno    |               1 |  1 | Desarrollo       |      120000 |   6000 |
  | 11 | 67389283A | Marta   | Herrera   | Gil       |               1 |  1 | Desarrollo       |      120000 |   6000 |
  |  2 | Y5575632D | Adela   | Salas     | Díaz      |               2 |  2 | Sistemas         |      150000 |  21000 |
  |  7 | 80576669X | Pilar   | Ruiz      | NULL      |               2 |  2 | Sistemas         |      150000 |  21000 |
  |  9 | 56399183D | Juan    | Gómez     | López     |               2 |  2 | Sistemas         |      150000 |  21000 |
  |  3 | R6970642B | Adolfo  | Rubio     | Flores    |               3 |  3 | Recursos Humanos |      280000 |  25000 |
  |  8 | 71651431Z | Pepe    | Ruiz      | Santana   |               3 |  3 | Recursos Humanos |      280000 |  25000 |
  |  4 | 77705545E | Adrián  | Suárez    | NULL      |               4 |  4 | Contabilidad     |      110000 |   3000 |
  |  5 | 17087203C | Marcos  | Loyola    | Méndez    |               5 |  5 | I+D              |      375000 | 380000 |
  | 10 | 46384486H | Diego   | Flores    | Salas     |               5 |  5 | I+D              |      375000 | 380000 |
  +----+-----------+---------+-----------+-----------+-----------------+----+------------------+-------------+--------+
  ```

  

2. Devuelve un listado con los empleados y los datos de los departamentos
     donde trabaja cada uno. Ordena el resultado, en primer lugar por el nombre
       del departamento (en orden alfabético) y en segundo lugar por los apellidos
       y el nombre de los empleados.

     ```sql
     SELECT  e.id , e.nif , e.nombre, e.apellido1, e.apellido2 , e.id_departamento , d.id, d.nombre, d.presupuesto, d.gastos 
     FROM empleado AS e,departamento AS d
     WHERE e.id_departamento = d.id ORDER BY d.nombre, e.apellido1, e.apellido2 , e.nombre;
     
     | id | nif       | nombre  | apellido1 | apellido2 | id_departamento | id | nombre           | presupuesto | gastos |
     +----+-----------+---------+-----------+-----------+-----------------+----+------------------+-------------+--------+
     |  4 | 77705545E | Adrián  | Suárez    | NULL      |               4 |  4 | Contabilidad     |      110000 |   3000 |
     | 11 | 67389283A | Marta   | Herrera   | Gil       |               1 |  1 | Desarrollo       |      120000 |   6000 |
     |  1 | 32481596F | Aarón   | Rivero    | Gómez     |               1 |  1 | Desarrollo       |      120000 |   6000 |
     |  6 | 38382980M | María   | Santana   | Moreno    |               1 |  1 | Desarrollo       |      120000 |   6000 |
     | 10 | 46384486H | Diego   | Flores    | Salas     |               5 |  5 | I+D              |      375000 | 380000 |
     |  5 | 17087203C | Marcos  | Loyola    | Méndez    |               5 |  5 | I+D              |      375000 | 380000 |
     |  3 | R6970642B | Adolfo  | Rubio     | Flores    |               3 |  3 | Recursos Humanos |      280000 |  25000 |
     |  8 | 71651431Z | Pepe    | Ruiz      | Santana   |               3 |  3 | Recursos Humanos |      280000 |  25000 |
     |  9 | 56399183D | Juan    | Gómez     | López     |               2 |  2 | Sistemas         |      150000 |  21000 |
     |  7 | 80576669X | Pilar   | Ruiz      | NULL      |               2 |  2 | Sistemas         |      150000 |  21000 |
     |  2 | Y5575632D | Adela   | Salas     | Díaz      |               2 |  2 | Sistemas         |      150000 |  21000 |
     +----+-----------+---------+-----------+-----------+-----------------+----+------------------+-------------+--------+
     ```

     

3. Devuelve un listado con el identificador y el nombre del departamento,
     solamente de aquellos departamentos que tienen empleados.

     ```sql
     SELECT d.id , d.nombre
     FROM empleado ,departamento AS d 
     WHERE empleado.id_departamento = d.id;
     +----+------------------+
     | id | nombre           |
     +----+------------------+
     |  1 | Desarrollo       |
     |  1 | Desarrollo       |
     |  1 | Desarrollo       |
     |  2 | Sistemas         |
     |  2 | Sistemas         |
     |  2 | Sistemas         |
     |  3 | Recursos Humanos |
     |  3 | Recursos Humanos |
     |  4 | Contabilidad     |
     |  5 | I+D              |
     |  5 | I+D              |
     +----+------------------+
     ```

     

4. Devuelve un listado con el identificador, el nombre del departamento y el
     valor del presupuesto actual del que dispone, solamente de aquellos
       departamentos que tienen empleados. El valor del presupuesto actual lo
       puede calcular restando al valor del presupuesto inicial
       (columna presupuesto) el valor de los gastos que ha generado
       (columna gastos).

     ```sql
     SELECT d.id , d.nombre, d.presupuesto , (d.presupuesto - d.gastos) AS presupuesto_actual
     FROM departamento AS d 
     WHERE d.id in (select empleado.id_departamento from empleado where empleado.id_departamento is not null);
     +----+------------------+-------------+--------------------+
     | id | nombre           | presupuesto | presupuesto_actual |
     +----+------------------+-------------+--------------------+
     |  1 | Desarrollo       |      120000 |             114000 |
     |  2 | Sistemas         |      150000 |             129000 |
     |  3 | Recursos Humanos |      280000 |             255000 |
     |  4 | Contabilidad     |      110000 |             107000 |
     |  5 | I+D              |      375000 |              -5000 |
     +----+------------------+-------------+--------------------+
     
     ```

     

5. Devuelve el nombre del departamento donde trabaja el empleado que tiene
     el nif 38382980M.

     ```SQL
     SELECT nombre 
     FROM departamento 
     WHERE id = (select id_departamento FROM empleado WHERE nif = '38382980M');
     
     +------------+
     | nombre     |
     +------------+
     | Desarrollo |
     +------------+
     ```

     

6. Devuelve el nombre del departamento donde trabaja el empleado Pepe Ruiz
     Santana.

     ```SQL
     SELECT D.nombre 
     FROM empleado AS E
     INNER JOIN departamento AS D ON E.id_departamento = D.id 
     WHERE E.nombre = 'Pepe' AND E.apellido1 = 'Ruiz' AND E.apellido2 = 'Santana';
     +------------------+
     | nombre           |
     +------------------+
     | Recursos Humanos |
     +------------------+
     ```

     

7. Devuelve un listado con los datos de los empleados que trabajan en el
     departamento de I+D. Ordena el resultado alfabéticamente.

     ```SQL
     SELECT E.id , E.nombre , E.apellido1 ,  E.apellido2 , E.id_departamento
     FROM empleado AS E 
     INNER JOIN departamento AS D ON E.id_departamento = D.id
     WHERE D.nombre = 'I+D' ORDER BY E.nombre ASC;
     +----+--------+-----------+-----------+-----------------+
     | id | nombre | apellido1 | apellido2 | id_departamento |
     +----+--------+-----------+-----------+-----------------+
     | 10 | Diego  | Flores    | Salas     |               5 |
     |  5 | Marcos | Loyola    | Méndez    |               5 |
     +----+--------+-----------+-----------+-----------------+
     ```

     

8. Devuelve un listado con los datos de los empleados que trabajan en el
     departamento de Sistemas, Contabilidad o I+D. Ordena el resultado
       alfabéticamente.

     ```sql
     SELECT E.id , E.nombre , E.apellido1 ,  E.apellido2 , E.id_departamento
     FROM empleado AS E 
     INNER JOIN departamento AS D ON E.id_departamento = D.id
     WHERE D.nombre IN ('I+D', 'sistemas', 'contabilidad') ORDER BY E.nombre ASC;
     
     +----+---------+-----------+-----------+-----------------+
     | id | nombre  | apellido1 | apellido2 | id_departamento |
     +----+---------+-----------+-----------+-----------------+
     |  2 | Adela   | Salas     | Díaz      |               2 |
     |  4 | Adrián  | Suárez    | NULL      |               4 |
     | 10 | Diego   | Flores    | Salas     |               5 |
     |  9 | Juan    | Gómez     | López     |               2 |
     |  5 | Marcos  | Loyola    | Méndez    |               5 |
     |  7 | Pilar   | Ruiz      | NULL      |               2 |
     +----+---------+-----------+-----------+-----------------+
     ```

     

9. Devuelve una lista con el nombre de los empleados que tienen los
     departamentos que no tienen un presupuesto entre 100000 y 200000 euros.

     ```sql
     SELECT E.nombre
     FROM empleado AS E
     INNER JOIN departamento AS D ON E.id_departamento = D.id
     WHERE D.presupuesto NOT BETWEEN 100000 AND 200000 ORDER BY E.nombre ASC;
     +--------+
     | nombre |
     +--------+
     | Adolfo |
     | Diego  |
     | Marcos |
     | Pepe   |
     +--------+
     ```

     

10. Devuelve un listado con el nombre de los departamentos donde existe
       algún empleado cuyo segundo apellido sea NULL. Tenga en cuenta que no
       debe mostrar nombres de departamentos que estén repetidos.

     ```sql
     SELECT D.nombre
     FROM empleado AS E
     INNER JOIN departamento AS D ON E.id_departamento = D.id
     WHERE apellido2 IS NULL;
     +--------------+
     | nombre       |
     +--------------+
     | Contabilidad |
     | Sistemas     |
     +--------------+
     ```

     

### Consultas multitabla (Composición externa)

Resuelva todas las consultas utilizando las cláusulas LEFT JOIN y RIGHT JOIN.

1. Devuelve un listado con todos los empleados junto con los datos de los
  departamentos donde trabajan. Este listado también debe incluir los
  empleados que no tienen ningún departamento asociado.

  ```SQL
  SELECT E.nombre, D.nombre AS departamento
  FROM empleado AS E
  LEFT JOIN departamento AS D ON E.id_departamento = D.id;
  +--------------+------------------+
  | nombre       | departamento     |
  +--------------+------------------+
  | Aarón        | Desarrollo       |
  | Adela        | Sistemas         |
  | Adolfo       | Recursos Humanos |
  | Adrián       | Contabilidad     |
  | Marcos       | I+D              |
  | María        | Desarrollo       |
  | Pilar        | Sistemas         |
  | Pepe         | Recursos Humanos |
  | Juan         | Sistemas         |
  | Diego        | I+D              |
  | Marta        | Desarrollo       |
  | Irene        | NULL             |
  | Juan Antonio | NULL             |
  +--------------+------------------+
  ```

  

2. Devuelve un listado donde sólo aparezcan aquellos empleados que no
  tienen ningún departamento asociado.

  ```SQL
  SELECT E.nombre, D.nombre AS departamento
  FROM empleado AS E
  LEFT JOIN departamento AS D ON E.id_departamento = D.id
  WHERE E.id_departamento IS NULL;
  +--------------+--------------+
  | nombre       | departamento |
  +--------------+--------------+
  | Irene        | NULL         |
  | Juan Antonio | NULL         |
  +--------------+--------------+
  ```

  

3. Devuelve un listado donde sólo aparezcan aquellos departamentos que no
  tienen ningún empleado asociado.

  ```SQL
  SELECT E.nombre, D.nombre AS departamento
  FROM empleado AS E
  RIGHT JOIN departamento AS D ON E.id_departamento = D.id
  WHERE E.id_departamento IS NULL;
  +--------+--------------+
  | nombre | departamento |
  +--------+--------------+
  | NULL   | Proyectos    |
  | NULL   | Publicidad   |
  +--------+--------------+
  ```

  

4. Devuelve un listado con todos los empleados junto con los datos de los
  departamentos donde trabajan. El listado debe incluir los empleados que no
  tienen ningún departamento asociado y los departamentos que no tienen
  ningún empleado asociado. Ordene el listado alfabéticamente por el
  nombre del departamento.

  ```SQL
  
  SELECT e.nombre,d.nombre AS departamento
  FROM empleado AS e 
  LEFT JOIN departamento AS d ON e.id_departamento  = d.id
  UNION 
  SELECT e.nombre,d.nombre AS departamento 
  FROM empleado AS e 
  RIGHT JOIN departamento AS d ON e.id_departamento = d.id
  WHERE e.id_departamento IS NULL;
  +--------------+------------------+
  | nombre       | departamento     |
  +--------------+------------------+
  | Aarón        | Desarrollo       |
  | Adela        | Sistemas         |
  | Adolfo       | Recursos Humanos |
  | Adrián       | Contabilidad     |
  | Marcos       | I+D              |
  | María        | Desarrollo       |
  | Pilar        | Sistemas         |
  | Pepe         | Recursos Humanos |
  | Juan         | Sistemas         |
  | Diego        | I+D              |
  | Marta        | Desarrollo       |
  | Irene        | NULL             |
  | Juan Antonio | NULL             |
  | NULL         | Proyectos        |
  | NULL         | Publicidad       |
  +--------------+------------------+
  ```

  

5. Devuelve un listado con los empleados que no tienen ningún departamento
  asociado y los departamentos que no tienen ningún empleado asociado.
  Ordene el listado alfabéticamente por el nombre del departamento.

```SQL
SELECT e.nombre,d.nombre AS departamento
FROM empleado AS e
LEFT JOIN departamento AS d ON e.id_departamento  = d.id
UNION
SELECT e.nombre,d.nombre AS departamento
FROM empleado AS e
RIGHT JOIN departamento AS d ON e.id_departamento  =d.id
WHERE e.id_departamento  IS NULL
ORDER BY departamento ASC;
+--------------+------------------+
| nombre       | departamento     |
+--------------+------------------+
| Irene        | NULL             |
| Juan Antonio | NULL             |
| Adrián       | Contabilidad     |
| Aarón        | Desarrollo       |
| María        | Desarrollo       |
| Marta        | Desarrollo       |
| Marcos       | I+D              |
| Diego        | I+D              |
| NULL         | Proyectos        |
| NULL         | Publicidad       |
| Adolfo       | Recursos Humanos |
| Pepe         | Recursos Humanos |
| Adela        | Sistemas         |
| Pilar        | Sistemas         |
| Juan         | Sistemas         |
+--------------+------------------+



```

### Consultas resumen



1. Calcula la suma del presupuesto de todos los departamentos.

   ```SQL
   SELECT SUM(d.presupuesto) AS presupuesto_de_todos_los_departamentos
   FROM departamento AS d;
   
   +----------------------------------------+
   | presupuesto_de_todos_los_departamentos |
   +----------------------------------------+
   |                                1035000 |
   +----------------------------------------+
   ```

   

2. Calcula la media del presupuesto de todos los departamentos.

   ```SQL
   SELECT AVG(d.presupuesto) AS MEDIA
   FROM departamento AS d;
   +--------------------+
   | MEDIA              |
   +--------------------+
   | 147857.14285714287 |
   +--------------------+
   ```

   

3. Calcula el valor mínimo del presupuesto de todos los departamentos.

   ```SQL
   SELECT MIN(d.presupuesto) AS Minimo
   FROM departamento AS d;
   +--------+
   | Minimo |
   +--------+
   |      0 |
   +--------+
   ```

   

4. Calcula el nombre del departamento y el presupuesto que tiene asignado,
  del departamento con menor presupuesto.

  ```sql
  SELECT d.nombre, d.presupuesto
  FROM departamento AS d
  WHERE d.presupuesto IN (SELECT MIN(presupuesto) FROM departamento);
  +------------+-------------+
  | nombre     | presupuesto |
  +------------+-------------+
  | Proyectos  |           0 |
  | Publicidad |           0 |
  +------------+-------------+
  ```

  

5. Calcula el valor máximo del presupuesto de todos los departamentos.

   ```sql
   SELECT  d.presupuesto
   FROM departamento AS d
   WHERE d.presupuesto IN (SELECT MAX(presupuesto) FROM departamento);
   +-------------+
   | presupuesto |
   +-------------+
   |      375000 |
   +-------------+
   ```

   

6. Calcula el nombre del departamento y el presupuesto que tiene asignado,
  del departamento con mayor presupuesto.

  ```sql
  SELECT d.nombre, d.presupuesto
  FROM departamento AS d
  WHERE d.presupuesto IN (SELECT MAX(presupuesto) FROM departamento);
  +--------+-------------+
  | nombre | presupuesto |
  +--------+-------------+
  | I+D    |      375000 |
  +--------+-------------+
  ```

  

7. Calcula el número total de empleados que hay en la tabla empleado.

   ```sql
   SELECT COUNT(e.id) AS cantidad_EMPLEADOS
   FROM empleado AS e;
   +--------------------+
   | cantidad_EMPLEADOS |
   +--------------------+
   |                 13 |
   +--------------------+
   ```

   

8. Calcula el número de empleados que no tienen NULL en su segundo
  apellido.

  ```sql
  SELECT COUNT(e.id) AS cantidad_NOT_NULL_EMPLEADOS
  FROM empleado AS e
  WHERE NOT e.apellido2 IS NULL;
  +-----------------------------+
  | cantidad_NOT_NULL_EMPLEADOS |
  +-----------------------------+
  |                          11 |
  +-----------------------------+
  ```

  

9. Calcula el número de empleados que hay en cada departamento. Tienes que
  devolver dos columnas, una con el nombre del departamento y otra con el
  número de empleados que tiene asignados.

  ```sql
  SELECT d.nombre AS Departamento, COUNT(e.id) AS Empleados
  FROM departamento AS d
  LEFT JOIN empleado AS e ON d.id = e.id_departamento
  GROUP BY d.nombre;
  +------------------+-----------+
  | Departamento     | Empleados |
  +------------------+-----------+
  | Desarrollo       |         3 |
  | Sistemas         |         3 |
  | Recursos Humanos |         2 |
  | Contabilidad     |         1 |
  | I+D              |         2 |
  | Proyectos        |         0 |
  | Publicidad       |         0 |
  +------------------+-----------+
  ```

  

10. Calcula el nombre de los departamentos que tienen más de 2 empleados. El
    resultado debe tener dos columnas, una con el nombre del departamento y
    otra con el número de empleados que tiene asignados.

    ```sql
    SELECT d.nombre AS Departamento, COUNT(e.id) AS empleados
    FROM departamento AS d
    LEFT JOIN empleado AS e ON d.id = e.id_departamento
    GROUP BY d.nombre
    HAVING COUNT(e.id) > 2;
    +--------------+-----------+
    | Departamento | empleados |
    +--------------+-----------+
    | Desarrollo   |         3 |
    | Sistemas     |         3 |
    +--------------+-----------+
    ```

    

11. Calcula el número de empleados que trabajan en cada uno de los
    departamentos. El resultado de esta consulta también tiene que incluir
    aquellos departamentos que no tienen ningún empleado asociado.

    ```sql
    SELECT d.nombre AS Departamento, COUNT(e.id) AS Total_empleados
    FROM departamento AS d
    LEFT JOIN empleado AS e ON d.id = e.id_departamento
    GROUP BY d.nombre;
    +------------------+-----------------+
    | Departamento     | Total_empleados |
    +------------------+-----------------+
    | Desarrollo       |               3 |
    | Sistemas         |               3 |
    | Recursos Humanos |               2 |
    | Contabilidad     |               1 |
    | I+D              |               2 |
    | Proyectos        |               0 |
    | Publicidad       |               0 |
    +------------------+-----------------+
    ```

    

12. Calcula el número de empleados que trabajan en cada unos de los
    departamentos que tienen un presupuesto mayor a 200000 euros.

    ```sql
    SELECT d.nombre AS Departamento, COUNT(e.id) AS Total_empleados
    FROM departamento AS d
    LEFT JOIN empleado AS e ON d.id = e.id_departamento
    WHERE d.presupuesto > 200000
    GROUP BY d.nombre;
    +------------------+-----------------+
    | Departamento     | Total_empleados |
    +------------------+-----------------+
    | Recursos Humanos |               2 |
    | I+D              |               2 |
    +------------------+-----------------+
    ```

    ### Subconsultas

    Con operadores básicos de comparación

    1. Devuelve un listado con todos los empleados que tiene el departamento
      de Sistemas. (Sin utilizar INNER JOIN).

      ```sql
      SELECT e.id ,e.nombre
      FROM empleado AS e
      WHERE e.id_departamento IN (SELECT d.id FROM departamento AS d WHERE d.nombre = 'Sistemas');
      +----+--------+
      | id | nombre |
      +----+--------+
      |  2 | Adela  |
      |  7 | Pilar  |
      |  9 | Juan   |
      +----+--------+
      ```

      

    2. Devuelve el nombre del departamento con mayor presupuesto y la cantidad
      que tiene asignada.

      ```sql
      SELECT d.nombre,d.presupuesto
      FROM departamento AS d
      WHERE d.presupuesto IN (SELECT MAX(presupuesto)FROM departamento);
      +--------+-------------+
      | nombre | presupuesto |
      +--------+-------------+
      | I+D    |      375000 |
      +--------+-------------+
      ```

      

    3. Devuelve el nombre del departamento con menor presupuesto y la cantidad
      que tiene asignada.

      ```sql
      SELECT d.nombre, d.presupuesto
      FROM departamento AS d
      WHERE d.presupuesto < ALL (SELECT presupuesto FROM departamento WHERE presupuesto <> d.presupuesto);
      +------------+-------------+
      | nombre     | presupuesto |
      +------------+-------------+
      | Proyectos  |           0 |
      | Publicidad |           0 |
      +------------+-------------+
      ```

      Subconsultas con ALL y ANY

    4. Devuelve el nombre del departamento con mayor presupuesto y la cantidad
      que tiene asignada. Sin hacer uso de MAX, ORDER BY ni LIMIT.

      ```sql
      SELECT d.nombre, d.presupuesto
      FROM departamento AS d
      WHERE d.presupuesto > ALL (SELECT presupuesto FROM departamento WHERE presupuesto <> d.presupuesto);
      +--------+-------------+
      | nombre | presupuesto |
      +--------+-------------+
      | I+D    |      375000 |
      +--------+-------------+
      1 row in set (0,00 sec)
      ```

      

    5. Devuelve el nombre del departamento con menor presupuesto y la cantidad
      que tiene asignada. Sin hacer uso de MIN, ORDER BY ni LIMIT.

      ```sql
      SELECT d.nombre, d.presupuesto
      FROM departamento AS d
      WHERE d.presupuesto < ALL (SELECT presupuesto FROM departamento WHERE presupuesto <> d.presupuesto);
      +------------+-------------+
      | nombre     | presupuesto |
      +------------+-------------+
      | Proyectos  |           0 |
      | Publicidad |           0 |
      +------------+-------------+
      2 rows in set (0,00 sec)
      ```

      

    6. Devuelve los nombres de los departamentos que tienen empleados
      asociados. (Utilizando ALL o ANY).

      ```sql
      SELECT DISTINCT  d.nombre
      FROM departamento AS d,empleado AS e
      WHERE e.id_departamento = ANY (SELECT id_departamento FROM empleado WHERE e.id_departamento = d.id)
      +------------------+
      | nombre           |
      +------------------+
      | Desarrollo       |
      | Sistemas         |
      | Recursos Humanos |
      | Contabilidad     |
      | I+D              |
      +------------------+
      5 rows in set (0,00 sec)
      ```

      

    7. Devuelve los nombres de los departamentos que no tienen empleados
      asociados. (Utilizando ALL o ANY).

      ```sql
      SELECT d.nombre
      FROM departamento AS d
      WHERE d.id NOT IN (SELECT DISTINCT id_departamento FROM empleado WHERE id_departamento IS NOT NULL);
      +------------+
      | nombre     |
      +------------+
      | Proyectos  |
      | Publicidad |
      +------------+
      2 rows in set (0,00 sec)
      ```

      Subconsultas con IN y NOT IN

    8. Devuelve los nombres de los departamentos que tienen empleados
      asociados. (Utilizando IN o NOT IN).

      ```sql
      SELECT d.nombre
      FROM departamento AS d
      WHERE id IN (SELECT DISTINCT id_departamento FROM empleado WHERE id_departamento IS NOT NULL);
      +------------------+
      | nombre           |
      +------------------+
      | Desarrollo       |
      | Sistemas         |
      | Recursos Humanos |
      | Contabilidad     |
      | I+D              |
      +------------------+
      5 rows in set (0,00 sec)
      ```

      

    9. Devuelve los nombres de los departamentos que no tienen empleados
      asociados. (Utilizando IN o NOT IN).

      ```
      SELECT d.nombre
      FROM departamento AS d
      WHERE NOT EXISTS (SELECT 1 FROM empleado as e WHERE e.id_departamento = d.id);
      +------------+
      | nombre     |
      +------------+
      | Proyectos  |
      | Publicidad |
      +------------+
      2 rows in set (0,00 sec)
      ```

      Subconsultas con EXISTS y NOT EXISTS

    10. Devuelve los nombres de los departamentos que tienen empleados
        asociados. (Utilizando EXISTS o NOT EXISTS).

        ```
        SELECT d.nombre
        FROM departamento AS d
        WHERE EXISTS (SELECT 1 FROM empleado as e WHERE e.id_departamento = d.id);
        +------------------+
        | nombre           |
        +------------------+
        | Desarrollo       |
        | Sistemas         |
        | Recursos Humanos |
        | Contabilidad     |
        | I+D              |
        +------------------+
        5 rows in set (0,00 sec)
        ```

        

    11. Devuelve los nombres de los departamentos que tienen empleados
        asociados. (Utilizando EXISTS o NOT EXISTS).

        ```
        SELECT d.nombre
        FROM departamento AS d
        WHERE EXISTS (SELECT 1 FROM empleado as e WHERE e.id_departamento = d.id);
        +------------------+
        | nombre           |
        +------------------+
        | Desarrollo       |
        | Sistemas         |
        | Recursos Humanos |
        | Contabilidad     |
        | I+D              |
        +------------------+
        5 rows in set (0,00 sec)
        
        ```

        