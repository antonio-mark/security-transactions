# PKI
## Componentes
- Autoridade de certificação (AC)
- Autoridade de registro
- Certificado Digital (x.509) = Relacionar uma chave pública com uma entidade 
    {Chave pública + Dados da entidade} (Precisa de integridade - assinatura digital, final do arquivo)


PU + Dados --> AC --> hash --> RSA (PR de AC) --> AD (assinatura digital) --> return [não mais usado, so pra solicitar certificado de site e assinatura de código]

Dados --> AC --> PUa e PRa --> PKS12 --> return [usado, nao garante integridade, navegadores nao possui mais acesso privilegiado]
