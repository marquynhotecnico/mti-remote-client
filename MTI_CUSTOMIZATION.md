# MTI Remote — personalização e compilação

## Escopo desta versão

Esta árvore deriva do RustDesk 1.4.7, commit upstream `0c86d4616298f09435f6236599b300964aa61460`, sob a licença GNU AGPL-3.0.

Alterações MTI:

- nome público: **MTI Remote**;
- paleta da janela confirmada no Portal MTI V6 em 24/10/2026: verde
  `#08784B` e verde de destaque `#0B9660`;
- servidor padrão de identificação: `179.198.108.1`;
- relay padrão: `179.198.108.1:21117`;
- chave pública do servidor incorporada ao cliente;
- metadados e nome do executável Windows personalizados;
- links públicos direcionados ao portal `https://remote.mtiinformatica.com.br`.

Nenhuma senha, chave privada, token ou credencial está armazenada nesta árvore. A chave incluída é a chave **pública** necessária para validar o servidor MTI.

O logotipo binário do cliente só será substituído por uma cópia derivada do
arquivo oficial `Logo MTI.jpeg` (Drive, 21/10/2026). Nenhum ícone azul já
presente na árvore deve ser apresentado como logotipo oficial MTI.

## Licença e disponibilização do código

A distribuição do executável modificado deve ser acompanhada por acesso ao código-fonte correspondente, incluindo estas alterações e scripts de construção, conforme a GNU AGPL-3.0. Os avisos de copyright do projeto original são preservados junto com a indicação das modificações MTI.

O nome e a identidade visual MTI não alteram a licença do código-base. A marca MTI pertence à MTI Soluções em Informática.

## Construção Windows

Dependências principais: Visual Studio Build Tools 2022 com C++, Rust estável, LLVM/Clang, CMake, vcpkg e Flutter 3.24.5. A receita de referência é a documentação oficial do projeto e o workflow `.github/workflows/flutter-build.yml` desta versão.

Com o ambiente preparado:

```powershell
python .\build.py --portable --hwcodec --flutter --vram
```

Saída esperada:

```text
MTI-Remote-1.4.7-Setup.exe
```

## Validação mínima antes de publicar

1. verificar assinatura e hash SHA-256 do pacote;
2. abrir em uma máquina Windows limpa;
3. confirmar nome, ícone e ausência de marca pública do projeto-base nas telas;
4. confirmar conexão apenas com o servidor MTI;
5. testar acesso autorizado, transferência de arquivo, áudio, elevação e encerramento;
6. desinstalar e confirmar remoção do serviço;
7. publicar o executável e o código-fonte correspondente no portal;
8. registrar versão, hash, data e resultado dos testes.
