Seeing the assembly using radare2 we can see the flag.
```
radare2 plainSight 
[0x080483b0]> pD 1000

            ;-- main:
            ;-- sym.main:
            0x080484ab    8d4c2404       lea ecx, dword [esp + 4]       ; 0x4 
            0x080484af    83e4f0         and esp, 0xfffffff0
            0x080484b2    ff71fc         push dword [ecx - 4]
            0x080484b5    55             push ebp
            0x080484b6    89e5           mov ebp, esp
            0x080484b8    51             push ecx
            0x080484b9    83ec14         sub esp, 0x14
            0x080484bc    83ec0c         sub esp, 0xc
            0x080484bf    6840860408     push str.Make_sure_you_pay_close_attention_ ; "Make sure you pay close attention!" @ 0x8048640
            0x080484c4    e8a7feffff     call sym.imp.puts ;0x08048370(unk) ; sym.imp.puts
            0x080484c9    83c410         add esp, 0x10
            0x080484cc    83ec0c         sub esp, 0xc
            0x080484cf    6863860408     push str.Okey__ready___y_n_   ; "Okey, ready? (y/n)" @ 0x8048663
            0x080484d4    e897feffff     call sym.imp.puts ;0x08048370(unk) ; sym.imp.puts
            0x080484d9    83c410         add esp, 0x10
            0x080484dc    a1c0980408     mov eax, dword [sym.stdout__GLIBC_2.0]  ; [0x80498c0:4]=0x3a434347  ; "GCC: (Debian 4.9.2-10) 4.9.2" @ 0x80498c0
            0x080484e1    83ec0c         sub esp, 0xc
            0x080484e4    50             push eax
            0x080484e5    e866feffff     call sym.imp.fflush ;0x08048350(unk) ; sym.imp.fflush
            0x080484ea    83c410         add esp, 0x10
            0x080484ed    83ec0c         sub esp, 0xc
            0x080484f0    6a01           push 1
            0x080484f2    e869feffff     call sym.imp.sleep ;0x08048360(unk) ; sym.imp.sleep
            0x080484f7    83c410         add esp, 0x10
            0x080484fa    83ec0c         sub esp, 0xc
            0x080484fd    6876860408     push str.Sorry__too_late_     ; "Sorry, too late!" @ 0x8048676
            0x08048502    e869feffff     call sym.imp.puts ;0x08048370(unk) ; sym.imp.puts
            0x08048507    83c410         add esp, 0x10
            0x0804850a    a1c0980408     mov eax, dword [sym.stdout__GLIBC_2.0]  ; [0x80498c0:4]=0x3a434347  ; "GCC: (Debian 4.9.2-10) 4.9.2" @ 0x80498c0
            0x0804850f    83ec0c         sub esp, 0xc
            0x08048512    50             push eax
            0x08048513    e838feffff     call sym.imp.fflush ;0x08048350(unk) ; sym.imp.fflush
            0x08048518    83c410         add esp, 0x10
            0x0804851b    b049           mov al, 0x49                  ; 'I'
            0x0804851d    b063           mov al, 0x63                  ; 'c'
            0x0804851f    b065           mov al, 0x65                  ; 'e'
            0x08048521    b043           mov al, 0x43                  ; 'C'
            0x08048523    b054           mov al, 0x54                  ; 'T'
            0x08048525    b046           mov al, 0x46                  ; 'F'
            0x08048527    b07b           mov al, 0x7b                  ; '{'
            0x08048529    b06c           mov al, 0x6c                  ; 'l'
            0x0804852b    b06f           mov al, 0x6f                  ; 'o'
            0x0804852d    b06f           mov al, 0x6f                  ; 'o'
            0x0804852f    b06b           mov al, 0x6b                  ; 'k'
            0x08048531    b05f           mov al, 0x5f                  ; '_'
            0x08048533    b06d           mov al, 0x6d                  ; 'm'
            0x08048535    b06f           mov al, 0x6f                  ; 'o'
            0x08048537    b06d           mov al, 0x6d                  ; 'm'
            0x08048539    b05f           mov al, 0x5f                  ; '_'
            0x0804853b    b049           mov al, 0x49                  ; 'I'
            0x0804853d    b05f           mov al, 0x5f                  ; '_'
            0x0804853f    b066           mov al, 0x66                  ; 'f'
            0x08048541    b06f           mov al, 0x6f                  ; 'o'
            0x08048543    b075           mov al, 0x75                  ; 'u'
            0x08048545    b06e           mov al, 0x6e                  ; 'n'
            0x08048547    b064           mov al, 0x64                  ; 'd'
            0x08048549    b05f           mov al, 0x5f                  ; '_'
            0x0804854b    b069           mov al, 0x69                  ; 'i'
            0x0804854d    b074           mov al, 0x74                  ; 't'
            0x0804854f    b07d           mov al, 0x7d                  ; '}'
            0x08048551    c745f4000000.  mov dword [ebp - 0xc], 0
  ========< 0x08048558    eb2f           jmp 0x8048589
  --------> 0x0804855a    83ec0c         sub esp, 0xc
            0x0804855d    6a01           push 1
            0x0804855f    e8fcfdffff     call sym.imp.sleep ;0x08048360(unk) ; sym.imp.sleep
            0x08048564    83c410         add esp, 0x10
            0x08048567    83ec0c         sub esp, 0xc
            0x0804856a    6a2e           push 0x2e                     ; '.'
            0x0804856c    e82ffeffff     call sym.imp.putchar ;0x080483a0(unk) ; sym.imp.putchar
            0x08048571    83c410         add esp, 0x10
            0x08048574    a1c0980408     mov eax, dword [sym.stdout__GLIBC_2.0]  ; [0x80498c0:4]=0x3a434347  ; "GCC: (Debian 4.9.2-10) 4.9.2" @ 0x80498c0
            0x08048579    83ec0c         sub esp, 0xc
            0x0804857c    50             push eax
            0x0804857d    e8cefdffff     call sym.imp.fflush ;0x08048350(unk) ; sym.imp.fflush
            0x08048582    83c410         add esp, 0x10
            0x08048585    8345f401       add dword [ebp - 0xc], 1
  --------> 0x08048589    837df403       cmp dword [ebp - 0xc], 3       ; [0x3:4]=0x1010146 
  ========< 0x0804858d    7ecb           jle 0x804855a
            0x0804858f    83ec0c         sub esp, 0xc
            0x08048592    6888860408     push str._nDang__that_was_fast__Did_you_get_it_ ; str._nDang__that_was_fast__Did_you_get_it_
            0x08048597    e8d4fdffff     call sym.imp.puts ;0x08048370(unk) ; sym.imp.puts
            0x0804859c    83c410         add esp, 0x10
            0x0804859f    b800000000     mov eax, 0
            0x080485a4    8b4dfc         mov ecx, dword [ebp - 4]
            0x080485a7    c9             leave
            0x080485a8    8d61fc         lea esp, dword [ecx - 4]
            0x080485ab    c3             ret
            0x080485ac    6690           nop
            0x080485ae    6690           nop
```
