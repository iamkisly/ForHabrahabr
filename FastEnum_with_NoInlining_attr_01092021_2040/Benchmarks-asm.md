## .NET 5.0.9 (5.0.921.35908), X64 RyuJIT
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

## .NET 5.0.9 (5.0.921.35908), X64 RyuJIT
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
       mov       r11,7F5CA72B03B8
       mov       rax,7F5CA72B03B8
       call      qword ptr [rax]
       mov       [rbp-10],rax
       mov       rdi,[rbp-10]
       mov       r11,7F5CA72B03C0
       mov       rax,7F5CA72B03C0
       call      qword ptr [rax]
       test      eax,eax
       je        short M00_L01
M00_L00:
       mov       rdi,[rbp-10]
       mov       r11,7F5CA72B03C8
       mov       rax,7F5CA72B03C8
       call      qword ptr [rax]
       add       ebx,eax
       mov       rdi,[rbp-10]
       mov       r11,7F5CA72B03C0
       mov       rax,7F5CA72B03C0
       call      qword ptr [rax]
       test      eax,eax
       jne       short M00_L00
M00_L01:
       mov       rdi,[rbp-10]
       mov       r11,7F5CA72B03D0
       mov       rax,7F5CA72B03D0
       call      qword ptr [rax]
       mov       eax,ebx
       lea       rsp,[rbp-8]
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
       mov       r11,7F5CA72B03D0
       mov       rax,7F5CA72B03D0
       call      qword ptr [rax]
M00_L02:
       nop
       add       rsp,8
       pop       rbx
       pop       rbp
       ret
; Total bytes of code 234
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
       movsxd    rsi,ebx
       lea       rdi,[rdi+rsi-1]
       test      ebx,ebx
       jl        near ptr M01_L02
       cmp       rdi,7FFFFFFF
       jg        near ptr M01_L02
       test      ebx,ebx
       jne       short M01_L00
       mov       rdi,7F5CA7FC0B78
       mov       esi,2
       call      CORINFO_HELP_CLASSINIT_SHARED_DYNAMICCLASS
       mov       rax,7F5C88000E08
       mov       rax,[rax]
       lea       rsp,[rbp-18]
       pop       rbx
       pop       r14
       pop       r15
       pop       rbp
       ret
M01_L00:
       mov       rdi,offset MT_System.Linq.Enumerable+RangeIterator
       call      CORINFO_HELP_NEWSFAST
       mov       r15,rax
       mov       rdi,7F5CA7CB0020
       mov       esi,24A
       call      CORINFO_HELP_GETSHARED_GCTHREADSTATIC_BASE
       mov       rdi,[rax+20]
       test      rdi,rdi
       jne       short M01_L01
       call      System.Threading.Thread.InitializeCurrentThread()
       mov       rdi,rax
M01_L01:
       cmp       [rdi],edi
       call      00007F5D2101BC10
       mov       [r15+8],eax
       mov       [r15+14],r14d
       add       ebx,r14d
       mov       [r15+18],ebx
       mov       rax,r15
       lea       rsp,[rbp-18]
       pop       rbx
       pop       r14
       pop       r15
       pop       rbp
       ret
M01_L02:
       mov       edi,1
       call      System.Linq.ThrowHelper.ThrowArgumentOutOfRangeException(System.Linq.ExceptionArgument)
       int       3
; Total bytes of code 199
```

## .NET 5.0.9 (5.0.921.35908), X64 RyuJIT
```assembly
; Benchmarks.ForeachWithYieldReturn()
       push      rbp
       push      rbx
       sub       rsp,18
       lea       rbp,[rsp+20]
       mov       [rbp-20],rsp
       xor       ebx,ebx
       mov       esi,[rdi+8]
       dec       esi
       xor       edi,edi
       mov       edx,1
       call      Benchmarks.MyRange(Int32, Int32, Int32)
       mov       rdi,rax
       mov       r11,7F4F2E0003B8
       mov       rax,7F4F2E0003B8
       call      qword ptr [rax]
       mov       [rbp-10],rax
       mov       rdi,[rbp-10]
       mov       r11,7F4F2E0003C0
       mov       rax,7F4F2E0003C0
       call      qword ptr [rax]
       test      eax,eax
       je        short M00_L01
M00_L00:
       mov       rdi,[rbp-10]
       mov       r11,7F4F2E0003C8
       mov       rax,7F4F2E0003C8
       call      qword ptr [rax]
       add       ebx,eax
       mov       rdi,[rbp-10]
       mov       r11,7F4F2E0003C0
       mov       rax,7F4F2E0003C0
       call      qword ptr [rax]
       test      eax,eax
       jne       short M00_L00
M00_L01:
       mov       rdi,[rbp-10]
       mov       r11,7F4F2E0003D0
       mov       rax,7F4F2E0003D0
       call      qword ptr [rax]
       mov       eax,ebx
       lea       rsp,[rbp-8]
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
       mov       r11,7F4F2E0003D0
       mov       rax,7F4F2E0003D0
       call      qword ptr [rax]
M00_L02:
       nop
       add       rsp,8
       pop       rbx
       pop       rbp
       ret
; Total bytes of code 241
```
```assembly
; Benchmarks.MyRange(Int32, Int32, Int32)
       push      rbp
       push      r15
       push      r14
       push      r12
       push      rbx
       lea       rbp,[rsp+20]
       mov       ebx,edi
       mov       r14d,esi
       mov       r15d,edx
       mov       rdi,offset MT_Benchmarks+<MyRange>d__10
       call      CORINFO_HELP_NEWSFAST
       mov       r12,rax
       mov       dword ptr [r12+8],0FFFFFFFE
       mov       rdi,7F4F2EA00020
       mov       esi,24A
       call      CORINFO_HELP_GETSHARED_GCTHREADSTATIC_BASE
       mov       rdi,[rax+20]
       test      rdi,rdi
       jne       short M01_L00
       call      System.Threading.Thread.InitializeCurrentThread()
       mov       rdi,rax
M01_L00:
       cmp       [rdi],edi
       call      00007F4FA7D73C10
       mov       [r12+10],eax
       mov       [r12+18],ebx
       mov       [r12+28],r14d
       mov       [r12+20],r15d
       mov       rax,r12
       pop       rbx
       pop       r12
       pop       r14
       pop       r15
       pop       rbp
       ret
; Total bytes of code 124
```

## .NET 5.0.9 (5.0.921.35908), X64 RyuJIT
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
       lea       rax,[rbp-20]
       mov       [rax],ebx
       mov       [rax+4],edi
       mov       rdi,[rbp-20]
       call      Library.Extensions.GetEnumerator(System.Range)
       mov       [rbp-18],rax
       mov       [rbp-10],edx
       lea       rax,[rbp-18]
       mov       edi,[rax]
       mov       esi,[rax+4]
       mov       eax,[rax+8]
       jmp       short M00_L01
M00_L00:
       add       ebx,eax
M00_L01:
       add       eax,esi
       cmp       eax,edi
       jne       short M00_L00
       mov       eax,ebx
       lea       rsp,[rbp-8]
       pop       rbx
       pop       rbp
       ret
M00_L02:
       call      System.ThrowHelper.ThrowValueArgumentOutOfRange_NeedNonNegNumException()
       int       3
; Total bytes of code 84
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
       jge       short M01_L02
       not       edi
       test      edi,edi
       jne       near ptr M01_L08
       test      eax,eax
       jge       short M01_L01
       not       eax
       test      eax,eax
       jne       near ptr M01_L08
       lea       rdi,[rbp-20]
       mov       dword ptr [rdi],80000000
       mov       dword ptr [rdi+4],1
       mov       dword ptr [rdi+8],0FFFFFFFF
M01_L00:
       mov       rax,[rbp-20]
       mov       edx,[rbp-18]
       lea       rsp,[rbp-8]
       pop       rbx
       pop       rbp
       ret
M01_L01:
       jmp       short M01_L04
M01_L02:
       test      eax,eax
       jge       short M01_L03
       not       eax
       test      eax,eax
       jne       short M01_L08
       dec       edi
       lea       rax,[rbp-20]
       mov       dword ptr [rax],80000000
       mov       dword ptr [rax+4],1
       mov       [rax+8],edi
       jmp       short M01_L00
M01_L03:
       jmp       short M01_L05
M01_L04:
       add       eax,2
       lea       rdi,[rbp-20]
       mov       [rdi],eax
       mov       dword ptr [rdi+4],1
       mov       dword ptr [rdi+8],0FFFFFFFF
       jmp       short M01_L00
M01_L05:
       cmp       edi,eax
       jge       short M01_L06
       inc       eax
       dec       edi
       mov       esi,1
       jmp       short M01_L07
M01_L06:
       dec       eax
       inc       edi
       mov       esi,0FFFFFFFF
M01_L07:
       lea       rdx,[rbp-20]
       mov       [rdx],eax
       mov       [rdx+4],esi
       mov       [rdx+8],edi
       jmp       short M01_L00
M01_L08:
       mov       rdi,offset MT_System.InvalidOperationException
       call      CORINFO_HELP_NEWSFAST
       mov       rbx,rax
       mov       edi,1
       mov       rsi,7F5F6CB1F3B8
       call      CORINFO_HELP_STRCNS
       mov       rsi,rax
       mov       rdi,rbx
       call      System.InvalidOperationException..ctor(System.String)
       mov       rdi,rbx
       call      CORINFO_HELP_THROW
       int       3
; Total bytes of code 256
```
**Method was not JITted yet.**
System.ThrowHelper.ThrowValueArgumentOutOfRange_NeedNonNegNumException()

## .NET 5.0.9 (5.0.921.35908), X64 RyuJIT
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
       lea       rax,[rbp-20]
       mov       [rax],ebx
       mov       [rax+4],edi
       mov       rdi,[rbp-20]
       call      Library.Extensions.GetEnumerator(System.Range)
       mov       [rbp-18],rax
       mov       [rbp-10],edx
       lea       rax,[rbp-18]
       mov       edi,[rax]
       mov       esi,[rax+4]
       mov       eax,[rax+8]
       jmp       short M00_L01
M00_L00:
       add       ebx,eax
M00_L01:
       add       eax,esi
       cmp       eax,edi
       jne       short M00_L00
       mov       eax,ebx
       lea       rsp,[rbp-8]
       pop       rbx
       pop       rbp
       ret
M00_L02:
       call      System.ThrowHelper.ThrowValueArgumentOutOfRange_NeedNonNegNumException()
       int       3
; Total bytes of code 84
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
       jge       short M01_L02
       not       edi
       test      edi,edi
       jne       near ptr M01_L08
       test      eax,eax
       jge       short M01_L01
       not       eax
       test      eax,eax
       jne       near ptr M01_L08
       lea       rdi,[rbp-20]
       mov       dword ptr [rdi],80000000
       mov       dword ptr [rdi+4],1
       mov       dword ptr [rdi+8],0FFFFFFFF
M01_L00:
       mov       rax,[rbp-20]
       mov       edx,[rbp-18]
       lea       rsp,[rbp-8]
       pop       rbx
       pop       rbp
       ret
M01_L01:
       jmp       short M01_L04
M01_L02:
       test      eax,eax
       jge       short M01_L03
       not       eax
       test      eax,eax
       jne       short M01_L08
       dec       edi
       lea       rax,[rbp-20]
       mov       dword ptr [rax],80000000
       mov       dword ptr [rax+4],1
       mov       [rax+8],edi
       jmp       short M01_L00
M01_L03:
       jmp       short M01_L05
M01_L04:
       add       eax,2
       lea       rdi,[rbp-20]
       mov       [rdi],eax
       mov       dword ptr [rdi+4],1
       mov       dword ptr [rdi+8],0FFFFFFFF
       jmp       short M01_L00
M01_L05:
       cmp       edi,eax
       jge       short M01_L06
       inc       eax
       dec       edi
       mov       esi,1
       jmp       short M01_L07
M01_L06:
       dec       eax
       inc       edi
       mov       esi,0FFFFFFFF
M01_L07:
       lea       rdx,[rbp-20]
       mov       [rdx],eax
       mov       [rdx+4],esi
       mov       [rdx+8],edi
       jmp       short M01_L00
M01_L08:
       mov       rdi,offset MT_System.InvalidOperationException
       call      CORINFO_HELP_NEWSFAST
       mov       rbx,rax
       mov       edi,1
       mov       rsi,7F65861AF3B8
       call      CORINFO_HELP_STRCNS
       mov       rsi,rax
       mov       rdi,rbx
       call      System.InvalidOperationException..ctor(System.String)
       mov       rdi,rbx
       call      CORINFO_HELP_THROW
       int       3
; Total bytes of code 256
```
**Method was not JITted yet.**
System.ThrowHelper.ThrowValueArgumentOutOfRange_NeedNonNegNumException()

## .NET 5.0.9 (5.0.921.35908), X64 RyuJIT
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
       lea       rsi,[rbp-18]
       mov       [rsi],eax
       mov       [rsi+4],edi
       mov       rdi,[rbp-18]
       call      Library.Extensions.GetEnumerator(System.Range)
       mov       [rbp-10],rax
       mov       [rbp-8],edx
       mov       rdi,[rbp-10]
       mov       esi,[rbp-8]
       call      Benchmarks.<ForeachWithRangeEnumeratorRawWithLocal>g__EnumerateItAll|14_0(Library.RangeEnumerator)
       nop
       lea       rsp,[rbp]
       pop       rbp
       ret
M00_L00:
       call      System.ThrowHelper.ThrowValueArgumentOutOfRange_NeedNonNegNumException()
       int       3
; Total bytes of code 71
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
       jge       short M01_L02
       not       edi
       test      edi,edi
       jne       near ptr M01_L08
       test      eax,eax
       jge       short M01_L01
       not       eax
       test      eax,eax
       jne       near ptr M01_L08
       lea       rdi,[rbp-20]
       mov       dword ptr [rdi],80000000
       mov       dword ptr [rdi+4],1
       mov       dword ptr [rdi+8],0FFFFFFFF
M01_L00:
       mov       rax,[rbp-20]
       mov       edx,[rbp-18]
       lea       rsp,[rbp-8]
       pop       rbx
       pop       rbp
       ret
M01_L01:
       jmp       short M01_L04
M01_L02:
       test      eax,eax
       jge       short M01_L03
       not       eax
       test      eax,eax
       jne       short M01_L08
       dec       edi
       lea       rax,[rbp-20]
       mov       dword ptr [rax],80000000
       mov       dword ptr [rax+4],1
       mov       [rax+8],edi
       jmp       short M01_L00
M01_L03:
       jmp       short M01_L05
M01_L04:
       add       eax,2
       lea       rdi,[rbp-20]
       mov       [rdi],eax
       mov       dword ptr [rdi+4],1
       mov       dword ptr [rdi+8],0FFFFFFFF
       jmp       short M01_L00
M01_L05:
       cmp       edi,eax
       jge       short M01_L06
       inc       eax
       dec       edi
       mov       esi,1
       jmp       short M01_L07
M01_L06:
       dec       eax
       inc       edi
       mov       esi,0FFFFFFFF
M01_L07:
       lea       rdx,[rbp-20]
       mov       [rdx],eax
       mov       [rdx+4],esi
       mov       [rdx+8],edi
       jmp       short M01_L00
M01_L08:
       mov       rdi,offset MT_System.InvalidOperationException
       call      CORINFO_HELP_NEWSFAST
       mov       rbx,rax
       mov       edi,1
       mov       rsi,7F8ADFC8F988
       call      CORINFO_HELP_STRCNS
       mov       rsi,rax
       mov       rdi,rbx
       call      System.InvalidOperationException..ctor(System.String)
       mov       rdi,rbx
       call      CORINFO_HELP_THROW
       int       3
; Total bytes of code 256
```
```assembly
; Benchmarks.<ForeachWithRangeEnumeratorRawWithLocal>g__EnumerateItAll|14_0(Library.RangeEnumerator)
       push      rbp
       sub       rsp,10
       lea       rbp,[rsp+10]
       mov       [rbp-10],rdi
       mov       [rbp-8],esi
       xor       eax,eax
       jmp       short M02_L01
M02_L00:
       add       eax,edi
M02_L01:
       mov       edi,[rbp-8]
       add       edi,[rbp-0C]
       mov       [rbp-8],edi
       cmp       edi,[rbp-10]
       jne       short M02_L00
       lea       rsp,[rbp]
       pop       rbp
       ret
; Total bytes of code 43
```
**Method was not JITted yet.**
System.ThrowHelper.ThrowValueArgumentOutOfRange_NeedNonNegNumException()

