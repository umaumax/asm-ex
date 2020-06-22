# arm

32bit arm EABI

## how to build
```
$AS -o hello_world.o hello_world.s
$LD -s -o hello_world hello_world.o
```

## ABI
[How to call a function from Arm Assembler \- Processors blog \- Processors \- Arm Community]( https://community.arm.com/developer/ip-products/processors/b/processors-ip-blog/posts/how-to-call-a-function-from-arm-assembler )

* r0-r3,r12: callee-saved
* r4-r11,r13-r15: caller-saved

[Procedure Call Standard for the Arm Architecture]( https://static.docs.arm.com/ihi0042/i/aapcs32.pdf )

返り値がdoubleの場合は`r0`と`r1`の両方が利用される

引数として、`r0-r3`以降は`[fp,#4]`,`[fp,#8]`,`[fp,#12]`のようにスタックが利用される

### 関数の呼び出し方
[ARM assembly branch to address inside register or memory \- Stack Overflow]( https://stackoverflow.com/questions/32304646/arm-assembly-branch-to-address-inside-register-or-memory )

## LR(リンクレジスタ)
* [CPUレジスタについて \| 学校では教えてくれないこと \| \[技術コラム集\]組込みの門 \| ユークエスト株式会社]( https://www.uquest.co.jp/embedded/learning/question03.html )

> リンクレジスタが無いx86などのCPUでは、呼び出し元のPC値をスタックに積んでおき、呼び出し元に戻るときにスタックか PC値を復元

## 例
* [ARM アセンブリ Hello, World on Raspberry Pi \| tech \- 氾濫原]( https://lowreal.net/2014/02/25/1 )
* [Assembly Programming on ARM Linux\(07\)]( https://www.mztn.org/slasm/arm07.html )
