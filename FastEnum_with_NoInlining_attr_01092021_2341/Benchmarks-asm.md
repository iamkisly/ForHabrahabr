## .NET 6.0.0 (6.0.21.37719), X64 RyuJIT
```assembly
; Benchmarks.ForWithCustomIncrement()
       push      rbp
       mov       rbp,rsp
       mov       eax,[rdi+8]
       xor       esi,esi
       mov       edi,[rdi+0C]
       xor       edx,edx
       test      eax,eax
       jle       short M00_L01
M00_L00:
       add       esi,edx
       add       edx,edi
       cmp       edx,eax
       jl        short M00_L00
M00_L01:
       mov       eax,esi
       pop       rbp
       ret
; Total bytes of code 30
```

## .NET 6.0.0 (6.0.21.37719), X64 RyuJIT
```assembly
; Benchmarks.ForeachWithEnumerableRange()
       push      rbp
       push      rbx
       sub       rsp,18
       lea       rbp,[rsp+20]
       mov       [rbp-20],rsp
       xor       ebx,ebx
       mov       esi,[rdi+8]
       xor       edi,edi
       call      System.Linq.Enumerable.Range(Int32, Int32)
       mov       rdi,rax
       mov       r11,7F3C59B00348
       mov       rax,7F3C59B00348
       call      qword ptr [rax]
       mov       rdi,rax
       mov       [rbp-10],rdi
       mov       r11,7F3C59B00350
       mov       rax,7F3C59B00350
       call      qword ptr [rax]
       test      eax,eax
       je        short M00_L01
M00_L00:
       mov       rdi,[rbp-10]
       mov       r11,7F3C59B00358
       mov       rax,7F3C59B00358
       call      qword ptr [rax]
       add       ebx,eax
       mov       rdi,[rbp-10]
       mov       r11,7F3C59B00350
       mov       rax,7F3C59B00350
       call      qword ptr [rax]
       test      eax,eax
       jne       short M00_L00
M00_L01:
       mov       rdi,[rbp-10]
       mov       r11,7F3C59B00360
       mov       rax,7F3C59B00360
       call      qword ptr [rax]
       mov       eax,ebx
       add       rsp,18
       pop       rbx
       pop       rbp
       ret
       push      rbp
       push      rbx
       push      rax
       mov       rbp,[rdi]
       mov       [rsp],rbp
       lea       rbp,[rbp+20]
       cmp       qword ptr [rbp-10],0
       je        short M00_L02
       mov       rdi,[rbp-10]
       mov       r11,7F3C59B00360
       mov       rax,7F3C59B00360
       call      qword ptr [rax]
M00_L02:
       nop
       add       rsp,8
       pop       rbx
       pop       rbp
       ret
; Total bytes of code 233
```
```assembly
; System.Linq.Enumerable.Range(Int32, Int32)
       push      rbp
       push      r15
       push      r14
       push      rbx
       push      rax
       lea       rbp,[rsp+20]
       mov       r14d,edi
       mov       ebx,esi
       movsxd    rdi,r14d
       movsxd    rax,ebx
       lea       rdi,[rdi+rax-1]
       test      ebx,ebx
       jl        short M01_L00
       cmp       rdi,7FFFFFFF
       jg        short M01_L00
       test      ebx,ebx
       je        short M01_L01
       mov       rdi,offset MT_System.Linq.Enumerable+RangeIterator
       call      CORINFO_HELP_NEWSFAST
       mov       r15,rax
       call      CORINFO_HELP_GETCURRENTMANAGEDTHREADID
       mov       [r15+8],eax
       mov       [r15+14],r14d
       add       ebx,r14d
       mov       [r15+18],ebx
       mov       rax,r15
       add       rsp,8
       pop       rbx
       pop       r14
       pop       r15
       pop       rbp
       ret
M01_L00:
       mov       edi,1
       call      System.Linq.ThrowHelper.ThrowArgumentOutOfRangeException(System.Linq.ExceptionArgument)
       int       3
M01_L01:
       mov       rdi,7F3C5A890BB0
       mov       esi,2
       call      CORINFO_HELP_CLASSINIT_SHARED_DYNAMICCLASS
       mov       rax,7F3C3C005AB8
       mov       rax,[rax]
       add       rsp,8
       pop       rbx
       pop       r14
       pop       r15
       pop       rbp
       ret
; Total bytes of code 152
```

## .NET 6.0.0 (6.0.21.37719), X64 RyuJIT
```assembly
; Benchmarks.ForeachWithYieldReturn()
       push      rbp
       push      r15
       push      r14
       push      rbx
       sub       rsp,18
       lea       rbp,[rsp+30]
       mov       [rbp-30],rsp
       xor       ebx,ebx
       mov       r14d,[rdi+8]
       dec       r14d
       mov       rdi,offset MT_Benchmarks+<MyRange>d__10
       call      CORINFO_HELP_NEWSFAST
       mov       r15,rax
       mov       dword ptr [r15+8],0FFFFFFFE
       call      CORINFO_HELP_GETCURRENTMANAGEDTHREADID
       mov       [r15+10],eax
       xor       edi,edi
       mov       [r15+18],edi
       mov       [r15+28],r14d
       mov       dword ptr [r15+20],1
       mov       rdi,r15
       mov       r11,7F4F82780348
       mov       rax,7F4F82780348
       call      qword ptr [rax]
       mov       r14,rax
       mov       [rbp-20],r14
       mov       rdi,r14
       mov       r11,7F4F82780350
       mov       rax,7F4F82780350
       call      qword ptr [rax]
       test      eax,eax
       je        short M00_L01
M00_L00:
       mov       rdi,r14
       mov       r11,7F4F82780358
       mov       rax,7F4F82780358
       call      qword ptr [rax]
       add       ebx,eax
       mov       rdi,r14
       mov       r11,7F4F82780350
       mov       rax,7F4F82780350
       call      qword ptr [rax]
       test      eax,eax
       jne       short M00_L00
M00_L01:
       mov       rdi,r14
       mov       r11,7F4F82780360
       mov       rax,7F4F82780360
       call      qword ptr [rax]
       mov       eax,ebx
       add       rsp,18
       pop       rbx
       pop       r14
       pop       r15
       pop       rbp
       ret
       push      rbp
       push      r15
       push      r14
       push      rbx
       push      rax
       mov       rbp,[rdi]
       mov       [rsp],rbp
       lea       rbp,[rbp+30]
       cmp       qword ptr [rbp-20],0
       je        short M00_L02
       mov       rdi,[rbp-20]
       mov       r11,7F4F82780360
       mov       rax,7F4F82780360
       call      qword ptr [rax]
M00_L02:
       nop
       add       rsp,8
       pop       rbx
       pop       r14
       pop       r15
       pop       rbp
       ret
; Total bytes of code 299
```

## .NET 6.0.0 (6.0.21.37719), X64 RyuJIT
```assembly
; Benchmarks.ForeachWithRangeEnumerator()
       push      rbp
       push      rbx
       sub       rsp,18
       lea       rbp,[rsp+20]
       xor       ebx,ebx
       mov       edi,[rdi+8]
       dec       edi
       test      edi,edi
       jl        short M00_L02
       mov       [rbp-20],ebx
       mov       [rbp-1C],edi
       mov       rdi,[rbp-20]
       call      Library.Extensions.GetEnumerator(System.Range)
       mov       [rbp-18],rax
       mov       [rbp-10],edx
       mov       eax,[rbp-18]
       mov       edi,[rbp-14]
       mov       esi,[rbp-10]
       add       esi,edi
       cmp       esi,eax
       je        short M00_L01
       nop       dword ptr [rax+rax]
M00_L00:
       add       ebx,esi
       add       esi,edi
       cmp       esi,eax
       jne       short M00_L00
M00_L01:
       mov       eax,ebx
       add       rsp,18
       pop       rbx
       pop       rbp
       ret
M00_L02:
       call      System.ThrowHelper.ThrowValueArgumentOutOfRange_NeedNonNegNumException()
       int       3
; Total bytes of code 87
```
```assembly
; Library.Extensions.GetEnumerator(System.Range)
       push      rbp
       push      rbx
       sub       rsp,18
       lea       rbp,[rsp+20]
       xor       eax,eax
       mov       [rbp-20],rax
       mov       [rbp-18],rax
       mov       [rbp-10],rdi
       mov       edi,[rbp-10]
       mov       eax,[rbp-0C]
       test      edi,edi
       jge       short M01_L01
       not       edi
       test      edi,edi
       jne       near ptr M01_L08
       test      eax,eax
       jge       short M01_L00
       mov       edi,eax
       not       edi
       test      edi,edi
       jne       near ptr M01_L08
       mov       dword ptr [rbp-20],80000000
       mov       dword ptr [rbp-1C],1
       mov       dword ptr [rbp-18],0FFFFFFFF
       jmp       short M01_L07
M01_L00:
       jmp       short M01_L03
M01_L01:
       test      eax,eax
       jge       short M01_L02
       not       eax
       test      eax,eax
       jne       short M01_L08
       dec       edi
       mov       dword ptr [rbp-20],80000000
       mov       dword ptr [rbp-1C],1
       mov       [rbp-18],edi
       jmp       short M01_L07
M01_L02:
       jmp       short M01_L04
M01_L03:
       add       eax,2
       mov       [rbp-20],eax
       mov       dword ptr [rbp-1C],1
       mov       dword ptr [rbp-18],0FFFFFFFF
       jmp       short M01_L07
M01_L04:
       cmp       edi,eax
       jge       short M01_L05
       inc       eax
       dec       edi
       mov       esi,1
       jmp       short M01_L06
M01_L05:
       dec       eax
       inc       edi
       mov       esi,0FFFFFFFF
M01_L06:
       mov       [rbp-20],eax
       mov       [rbp-1C],esi
       mov       [rbp-18],edi
M01_L07:
       mov       rax,[rbp-20]
       mov       edx,[rbp-18]
       add       rsp,18
       pop       rbx
       pop       rbp
       ret
M01_L08:
       mov       rdi,offset MT_System.InvalidOperationException
       call      CORINFO_HELP_NEWSFAST
       mov       rbx,rax
       mov       edi,1
       mov       rsi,7F3758614F00
       call      CORINFO_HELP_STRCNS
       mov       rsi,rax
       mov       rdi,rbx
       call      System.InvalidOperationException..ctor(System.String)
       mov       rdi,rbx
       call      CORINFO_HELP_THROW
       int       3
; Total bytes of code 246
```
**Method was not JITted yet.**
System.ThrowHelper.ThrowValueArgumentOutOfRange_NeedNonNegNumException()

## .NET 6.0.0 (6.0.21.37719), X64 RyuJIT
```assembly
; Benchmarks.ForeachWithRangeEnumeratorRaw()
       push      rbp
       push      rbx
       sub       rsp,18
       lea       rbp,[rsp+20]
       xor       ebx,ebx
       mov       edi,[rdi+8]
       dec       edi
       test      edi,edi
       jl        short M00_L02
       mov       [rbp-20],ebx
       mov       [rbp-1C],edi
       mov       rdi,[rbp-20]
       call      Library.Extensions.GetEnumerator(System.Range)
       mov       [rbp-18],rax
       mov       [rbp-10],edx
       mov       eax,[rbp-18]
       mov       edi,[rbp-14]
       mov       esi,[rbp-10]
       add       esi,edi
       cmp       esi,eax
       je        short M00_L01
       nop       dword ptr [rax+rax]
M00_L00:
       add       ebx,esi
       add       esi,edi
       cmp       esi,eax
       jne       short M00_L00
M00_L01:
       mov       eax,ebx
       add       rsp,18
       pop       rbx
       pop       rbp
       ret
M00_L02:
       call      System.ThrowHelper.ThrowValueArgumentOutOfRange_NeedNonNegNumException()
       int       3
; Total bytes of code 87
```
```assembly
; Library.Extensions.GetEnumerator(System.Range)
       push      rbp
       push      rbx
       sub       rsp,18
       lea       rbp,[rsp+20]
       xor       eax,eax
       mov       [rbp-20],rax
       mov       [rbp-18],rax
       mov       [rbp-10],rdi
       mov       edi,[rbp-10]
       mov       eax,[rbp-0C]
       test      edi,edi
       jge       short M01_L01
       not       edi
       test      edi,edi
       jne       near ptr M01_L08
       test      eax,eax
       jge       short M01_L00
       mov       edi,eax
       not       edi
       test      edi,edi
       jne       near ptr M01_L08
       mov       dword ptr [rbp-20],80000000
       mov       dword ptr [rbp-1C],1
       mov       dword ptr [rbp-18],0FFFFFFFF
       jmp       short M01_L07
M01_L00:
       jmp       short M01_L03
M01_L01:
       test      eax,eax
       jge       short M01_L02
       not       eax
       test      eax,eax
       jne       short M01_L08
       dec       edi
       mov       dword ptr [rbp-20],80000000
       mov       dword ptr [rbp-1C],1
       mov       [rbp-18],edi
       jmp       short M01_L07
M01_L02:
       jmp       short M01_L04
M01_L03:
       add       eax,2
       mov       [rbp-20],eax
       mov       dword ptr [rbp-1C],1
       mov       dword ptr [rbp-18],0FFFFFFFF
       jmp       short M01_L07
M01_L04:
       cmp       edi,eax
       jge       short M01_L05
       inc       eax
       dec       edi
       mov       esi,1
       jmp       short M01_L06
M01_L05:
       dec       eax
       inc       edi
       mov       esi,0FFFFFFFF
M01_L06:
       mov       [rbp-20],eax
       mov       [rbp-1C],esi
       mov       [rbp-18],edi
M01_L07:
       mov       rax,[rbp-20]
       mov       edx,[rbp-18]
       add       rsp,18
       pop       rbx
       pop       rbp
       ret
M01_L08:
       mov       rdi,offset MT_System.InvalidOperationException
       call      CORINFO_HELP_NEWSFAST
       mov       rbx,rax
       mov       edi,1
       mov       rsi,7FCC88294F00
       call      CORINFO_HELP_STRCNS
       mov       rsi,rax
       mov       rdi,rbx
       call      System.InvalidOperationException..ctor(System.String)
       mov       rdi,rbx
       call      CORINFO_HELP_THROW
       int       3
; Total bytes of code 246
```
**Method was not JITted yet.**
System.ThrowHelper.ThrowValueArgumentOutOfRange_NeedNonNegNumException()

## .NET 6.0.0 (6.0.21.37719), X64 RyuJIT
```assembly
; Benchmarks.ForeachWithRangeEnumeratorRawWithLocal()
       push      rbp
       sub       rsp,20
       lea       rbp,[rsp+20]
       mov       edi,[rdi+8]
       dec       edi
       test      edi,edi
       jl        short M00_L00
       xor       eax,eax
       mov       [rbp-18],eax
       mov       [rbp-14],edi
       mov       rdi,[rbp-18]
       call      Library.Extensions.GetEnumerator(System.Range)
       mov       [rbp-10],rax
       mov       [rbp-8],edx
       mov       rdi,[rbp-10]
       mov       esi,[rbp-8]
       add       rsp,20
       pop       rbp
       jmp       near ptr Benchmarks.<ForeachWithRangeEnumeratorRawWithLocal>g__EnumerateItAll|14_0(Library.RangeEnumerator)
M00_L00:
       call      System.ThrowHelper.ThrowValueArgumentOutOfRange_NeedNonNegNumException()
       int       3
; Total bytes of code 66
```
```assembly
; Library.Extensions.GetEnumerator(System.Range)
       push      rbp
       push      rbx
       sub       rsp,18
       lea       rbp,[rsp+20]
       xor       eax,eax
       mov       [rbp-20],rax
       mov       [rbp-18],rax
       mov       [rbp-10],rdi
       mov       edi,[rbp-10]
       mov       eax,[rbp-0C]
       test      edi,edi
       jge       short M01_L01
       not       edi
       test      edi,edi
       jne       near ptr M01_L08
       test      eax,eax
       jge       short M01_L00
       mov       edi,eax
       not       edi
       test      edi,edi
       jne       near ptr M01_L08
       mov       dword ptr [rbp-20],80000000
       mov       dword ptr [rbp-1C],1
       mov       dword ptr [rbp-18],0FFFFFFFF
       jmp       short M01_L07
M01_L00:
       jmp       short M01_L03
M01_L01:
       test      eax,eax
       jge       short M01_L02
       not       eax
       test      eax,eax
       jne       short M01_L08
       dec       edi
       mov       dword ptr [rbp-20],80000000
       mov       dword ptr [rbp-1C],1
       mov       [rbp-18],edi
       jmp       short M01_L07
M01_L02:
       jmp       short M01_L04
M01_L03:
       add       eax,2
       mov       [rbp-20],eax
       mov       dword ptr [rbp-1C],1
       mov       dword ptr [rbp-18],0FFFFFFFF
       jmp       short M01_L07
M01_L04:
       cmp       edi,eax
       jge       short M01_L05
       inc       eax
       dec       edi
       mov       esi,1
       jmp       short M01_L06
M01_L05:
       dec       eax
       inc       edi
       mov       esi,0FFFFFFFF
M01_L06:
       mov       [rbp-20],eax
       mov       [rbp-1C],esi
       mov       [rbp-18],edi
M01_L07:
       mov       rax,[rbp-20]
       mov       edx,[rbp-18]
       add       rsp,18
       pop       rbx
       pop       rbp
       ret
M01_L08:
       mov       rdi,offset MT_System.InvalidOperationException
       call      CORINFO_HELP_NEWSFAST
       mov       rbx,rax
       mov       edi,1
       mov       rsi,7F543D4E5380
       call      CORINFO_HELP_STRCNS
       mov       rsi,rax
       mov       rdi,rbx
       call      System.InvalidOperationException..ctor(System.String)
       mov       rdi,rbx
       call      CORINFO_HELP_THROW
       int       3
; Total bytes of code 246
```
```assembly
; Benchmarks.<ForeachWithRangeEnumeratorRawWithLocal>g__EnumerateItAll|14_0(Library.RangeEnumerator)
       push      rbp
       sub       rsp,10
       lea       rbp,[rsp+10]
       mov       [rbp-10],rdi
       mov       [rbp-8],esi
       xor       eax,eax
       mov       edi,[rbp-8]
       add       edi,[rbp-0C]
       mov       [rbp-8],edi
       mov       esi,[rbp-10]
       cmp       edi,esi
       je        short M02_L01
M02_L00:
       mov       edi,[rbp-8]
       add       eax,edi
       add       edi,[rbp-0C]
       mov       [rbp-8],edi
       cmp       edi,esi
       jne       short M02_L00
M02_L01:
       add       rsp,10
       pop       rbp
       ret
; Total bytes of code 56
```
**Method was not JITted yet.**
System.ThrowHelper.ThrowValueArgumentOutOfRange_NeedNonNegNumException()

