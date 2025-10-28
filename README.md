# 🧠 Assembly Language

## 📘 O que é Assembly?

Assembly (ou linguagem de montagem) é uma linguagem de baixo nível usada para programar diretamente o hardware do computador. Ela serve como uma ponte entre o código de máquina (binário) e as linguagens de alto nível como C, Java ou Python.
Cada instrução em Assembly corresponde quase diretamente a uma instrução do processador (CPU).

## ⚙️ Características principais

* 🔹 Baixo nível – próximo ao código binário que o processador entende.
* 🔹 Arquitetura dependente – cada processador (Intel, ARM, etc.) possui seu próprio conjunto de instruções.
* 🔹 Controle total do hardware – acesso direto a registradores, memória e dispositivos.
* 🔹 Altíssimo desempenho, mas difícil de escrever e manter.

## 🧩 Estrutura básica de um programa Assembly

Um código Assembly é geralmente dividido em seções:

```asm
section .data       ; Dados estáticos (variáveis iniciais)
    msg db "Olá, mundo!", 0Ah

section .bss        ; Dados não inicializados
    num resb 1

section .text       ; Código executável
    global _start

_start:
    mov eax, 4          ; syscall: write
    mov ebx, 1          ; saída padrão
    mov ecx, msg        ; mensagem
    mov edx, 13         ; tamanho
    int 0x80            ; chamada de sistema

    mov eax, 1          ; syscall: exit
    mov ebx, 0          ; código de saída
    int 0x80

```

Esse exemplo imprime “Olá, mundo!” no terminal Linux usando Assembly x86.

## 🧮 Conceitos importantes

| Conceito | Descriçãon |
|----------|------------|
| Registradores |	Pequenas áreas de armazenamento dentro da CPU (ex: eax, ebx, ecx). |
|Instruções|	Comandos básicos que a CPU executa (ex: mov, add, sub).|
|Syscalls|	Chamadas de sistema usadas para interagir com o SO (ex: imprimir texto, sair do programa).|
|Labels|	Marcadores usados para identificar locais no código (semelhantes a funções).|

## 🧰 Montadores populares

|Montador|	Descrição|
|--------|-----------|
|NASM	|(Netwide Assembler) – Muito usado em Linux e Windows.|
|MASM	|(Microsoft Assembler) – Usado principalmente em Windows.|
|GAS	|(GNU Assembler) – Usado com o compilador GCC.|

## 🧪 Compilando e executando (NASM no Linux)


