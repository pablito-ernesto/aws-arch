# aws-arch


## Hands On

### Route 53
#### Setup
 * 3 **ec2** instances on different regions. [With user data](https://github.com/pablito-ernesto/aws-arch/blob/b67aecba6dee230b9293da751f59ee0496947bb4/code/route53/user-data.sh).
 * 1 domain.
 * In all cases the TTL must be a think to watch.

##### Multivalue
 * Crear una hosted zone 
 * Registro A con multiples IPs
 * Validar que se cae en los distintos servers

##### Weighted
 * Registros A con peso relativo
 * Validar que cae con más probabilidad en uno que en otro

##### Latency
 * Registros del tipo latency
 * Validar con alguna VPN que cambia de region.

##### Geo Proximity
 * Registros del tipo geo
 * Validar con alguna VPN que cambia de region.

##### Geo Proximity Bias
 * Registros del tipo geo poner un índice arbitrario
 * Validar con alguna VPN que cambia de región.

##### Heath Checks
 * Registros con health checks
 * Validar que invalida el NS cuando el health check da error.

##### Heath Checks II
 * Crear health checks 
 * Crear un health check calculado en base a los otros
 
 
#### S3

##### Preparación
* Crear un bucket privado.

##### Subir File
 * Subir un file 
 * Validar que se puede acceder mediante la signed URL
 * Versionar

##### Activar el versionado 
 * Subir varias versiones del mismo file

##### Encriptación SSE-S3
 * Subir un file encriptado
 * Validar que quedó con la encriptación correcta.

##### Encriptación SSE-KMS
 * Subir un file encriptado
 * Validar que quedó con la encriptación correcta.

##### Crear una policy
 * Crear un policie que no deje hacer put object si no esta encriptado con AES256 
 * Tips: s3:x-amz-server-side-encryption
 * Validar que si se hace upload sin encriptar falla
 * Validar que si se hace upload encriptado sale ok 
 * Validar que si se hace upload encriptado con KMS falla

##### Crear un sitio estático
 * Marcar el bucket como sitio estático.
 * Marcar como Publico. 
 * Crear una policy que tenga allow para get.
 * Subir index y error html.
 * Validar que el sitio rederiza ok.

##### CORS
 * Crear un bucket nuevo.
 * Configurarlo como un sitio estático.
 * Habilitar CORS para el bucket inicial.
 * Obtener desde el sitio inicial un recurso del segundo sitio.






