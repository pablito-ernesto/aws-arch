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
 *Validar que cae con más probabilidad en uno que en otro

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
