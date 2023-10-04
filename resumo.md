# Public Key Infrastructure (PKI) - Infraestrutura de Chave Pública

A PKI é um conjunto de tecnologias e práticas que permite a gestão segura de chaves criptográficas e a garantia da autenticidade e integridade das informações em comunicações digitais. Ela é amplamente utilizada para estabelecer confiança em ambientes digitais, como a Internet. A PKI envolve vários componentes essenciais:

1. Autoridade de Certificação (AC):
Uma AC é uma entidade confiável que emite e gerencia certificados digitais.
Ela verifica a identidade dos titulares dos certificados antes de emitir certificados.
A AC gera um certificado digital que contém a chave pública do titular, informações de identidade e uma assinatura digital da AC para autenticidade e integridade.

2. Autoridade de Registro (AR):
A AR atua como intermediária entre os solicitantes de certificados e a AC.
Ela coleta e verifica as informações de identidade dos solicitantes antes de encaminhá-las à AC para emissão de certificados.

3. Certificado Digital (x.509):
Um certificado digital é um documento eletrônico que associa uma chave pública a uma entidade (pessoa, servidor, dispositivo).
Ele contém informações como o nome da entidade, chave pública, datas de validade e uma assinatura digital da AC.
A assinatura digital da AC garante a autenticidade do certificado e a integridade dos dados.

4. Processo de Emissão de Certificados:
Quando alguém solicita um certificado, os dados são submetidos à AC.
A AC cria um resumo (hash) dos dados e usa sua chave privada para criar uma assinatura digital.
O certificado é emitido com a chave pública associada à entidade e a assinatura digital da AC, garantindo sua autenticidade e integridade.

5. Usos de Certificados:
Certificados digitais são usados para autenticar entidades em comunicações seguras na Internet.
Eles são essenciais em protocolos como SSL/TLS para proteger conexões HTTPS, garantindo que os sites sejam autênticos e as comunicações sejam criptografadas.
Além disso, certificados são usados para assinaturas digitais, autenticação em redes corporativas, e-mail seguro e muito mais.

Correções/Comentários:
O termo "RSA" refere-se a um algoritmo de criptografia assimétrica usado na geração de pares de chaves (pública e privada) e na assinatura digital. Embora o RSA seja frequentemente usado em PKIs, não é o único algoritmo disponível.
O formato PKCS #12 (PFX) é usado para armazenar chaves privadas e certificados em um único arquivo protegido por senha, facilitando sua exportação e importação em diferentes sistemas.





# Caminho de Certificação em uma Infraestrutura de Chave Pública (ICP)

Autoridade de Certificação Raiz (AC Raiz):
Toda ICP começa com uma AC Raiz, que é a autoridade de nível mais alto na hierarquia.
A AC Raiz emite seu próprio certificado digital, que é autoassinado, ou seja, a AC Raiz assina seu próprio certificado.
O certificado da AC Raiz é amplamente distribuído e confiável globalmente, servindo como ponto de partida para a confiança em certificados digitais.

Autoridade de Certificação Subordinada (AC Subordinada):
A AC Raiz pode emitir certificados para ACs subordinadas, criando assim uma hierarquia.
Essas ACs subordinadas podem, por sua vez, emitir certificados para entidades finais, como sites, servidores, ou indivíduos.

Entidade Final (por exemplo, google.com):
As ACs subordinadas emitem certificados para entidades finais, como sites, identificando-os de forma única.
Ao acessar um site, um usuário recebe o certificado da entidade final, como o certificado SSL/TLS do site google.com.

Construção do Caminho de Certificação:
Para validar a autenticidade do certificado da entidade final, o cliente (por exemplo, um navegador) pode construir um caminho de certificação.
Isso é feito seguindo uma série de certificados, começando pelo certificado da entidade final e subindo na hierarquia de ACs até chegar à AC Raiz.
O cliente usa a extensão AIA (Authority Information Access) nos certificados para obter informações sobre onde encontrar os certificados das ACs superiores na hierarquia.

Validação do Caminho de Certificação:
O cliente verifica se cada certificado no caminho de certificação é válido.
Isso envolve verificar a assinatura digital de cada certificado, a data de validade e se o certificado não foi revogado.
A revogação é verificada através de listas de certificados revogados (CRLs) ou serviços de validação online (OCSP).

Restrições de Uso (Constraints):
Os certificados digitais podem conter informações sobre seu uso permitido. Por exemplo, um certificado pode ser restrito para uso exclusivo em e-mail, enquanto outro pode ser designado para assinatura de código.
Essas restrições garantem que os certificados sejam usados apenas para os fins pretendidos e impedem seu uso inadequado.

Em resumo, uma ICP é uma estrutura hierárquica que começa com uma AC Raiz, que emite certificados para ACs subordinadas e entidades finais. Para estabelecer confiança nos certificados digitais, os clientes constroem um caminho de certificação, validam cada certificado nesse caminho e verificam as restrições de uso. Isso garante a autenticidade e a integridade das comunicações seguras na Internet e em outras aplicações que dependem de certificados digitais.

