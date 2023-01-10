# Software Architecture

## Principios

### Resiliencia
- Sistemas distribuídos devem ser construídos de modo a que cada nó esteja em sintonia com os outros nós.
- Health checks são usados para verificar se um sistema está on, e se possível a qualidade do disponível. Pode ser importante que o health check verifique o tempo de resposta a recursos importantes.
- Rate limit: é importante o desenvolverdor saiba os limites que o sistema suporta, por exemplo, requisições por segundo.
- Circuit breaker: a fim de prevenir a sobrecarga de requisições, o sistema passa a retornar 500 a todos os seus clientes.
- API Gateway: uma forma de centralizar todas as requisições de um sistema.
- Service Mesh: cada nó de uma rede usam um proxy para se comunicar com outros nós a fim de poder ter uma monitoramente e gestão melhor da rede.