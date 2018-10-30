# Polynomial

> 这是 shesl 同学自己完成的，为了完成数据结构作业写的 c++ 类库

## 运行方式

如果您有 `bash` 环境，可以直接运行 `run.sh` 这个脚本：

```bash
$ ./run.sh
```



如果您只有 `g++` 环境，可以通过 `make` 命令编译 c++ 程序：

```bash
$ make
```

通过以下两个命令分别测试整数为系数，以浮点数为系数的多项式加减乘法：

```bash
$ ./main.exe `python gnrint.py`
# 测试整数

$ ./main.exe `python gnrdouble.py`
# 测试浮点数
```

## 说明

本库派生自 STL list 库，未应用傅里叶变化进行计算，welcome to PR。

## 一个测试结果

### `int_output.txt`

| operator |                      result                       |
| :------: | :-----------------------------------------------: |
|   P1:    |                   $$-7x^{-6}$$                    |
|   P2:    |     $$-8x^{-8}+8x^{-4}+8x^{1}-5x^{4}+8x^{8}$$     |
|  P1+P2:  | $$-8x^{-8}-7x^{-6}+8x^{-4}+8x^{1}-5x^{4}+8x^{8}$$ |
|  P1-P2:  | $$8x^{-8}-7x^{-6}-8x^{-4}-8x^{1}+5x^{4}-8x^{8}$$  |
|  P1*P2:  | $$56x^{-14}-56x^{-10}-56x^{-5}+35x^{-2}-56x^{2}$$ |
|  P1/P2:  |                       $$0$$                       |
|  P1%P2:  |                   $$-7x^{-6}$$                    |
| P1'(x):  |                   $$42x^{-7}$$                    |
| P2'(x):  |      $$64x^{-9}-32x^{-5}+8-20x^{3}+64x^{7}$$      |

| operator |                            result                            |
| :------: | :----------------------------------------------------------: |
|   P1:    |   $$1x^{-8}-2x^{-4}-6x^{-2}+1x^{-1}-6x^{1}+1x^{4}+5x^{6}$$   |
|   P2:    |          $$-2x^{-8}+2x^{-6}+6x^{-1}+5x^{5}-5x^{6}$$          |
|  P1+P2:  | $$-1x^{-8}+2x^{-6}-2x^{-4}-6x^{-2}+7x^{-1}-6x^{1}+1x^{4}+5x^{5}$$ |
|  P1-P2:  | $$3x^{-8}-2x^{-6}-2x^{-4}-6x^{-2}-5x^{-1}-6x^{1}+1x^{4}-5x^{5}+10x^{6}$$ |
|  P1*P2:  | $$-2x^{-16}+2x^{-14}+4x^{-12}+8x^{-10}+4x^{-9}-12x^{-8}+14x^{-7}-24x^{-5}-2x^{-4}-31x^{-3}+1x^{-2}-8x^{-2}-26-10x^{1}+10x^{2}-24x^{3}+35x^{4}+25x^{5}-30x^{6}+30x^{7}+5x^{9}-5x^{10}+25x^{11}-25x^{12}$$ |
|  P1/P2:  |                            $$0$$                             |
|  P1%P2:  |   $$1x^{-8}-2x^{-4}-6x^{-2}+1x^{-1}-6x^{1}+1x^{4}+5x^{6}$$   |
| P1'(x):  |    $$-8x^{-9}+8x^{-5}+12x^{-3}-1x^{-2}-6+4x^{3}+30x^{5}$$    |
| P2'(x):  |        $$16x^{-9}-12x^{-7}-6x^{-2}+25x^{4}-30x^{5}$$         |

| operator |                            result                            |
| :------: | :----------------------------------------------------------: |
|   P1:    | $$-8x^{-7}+8x^{-6}-3x^{-5}+4x^{-3}+10x^{4}+4x^{5}-10x^{7}+10x^{10}$$ |
|   P2:    |                         $$7x^{-2}$$                          |
|  P1+P2:  | $$-8x^{-7}+8x^{-6}-3x^{-5}+4x^{-3}+7x^{-2}+10x^{4}+4x^{5}-10x^{7}+10x^{10}$$ |
|  P1-P2:  | $$-8x^{-7}+8x^{-6}-3x^{-5}+4x^{-3}-7x^{-2}+10x^{4}+4x^{5}-10x^{7}+10x^{10}$$ |
|  P1*P2:  | $$-56x^{-9}+56x^{-8}-21x^{-7}+28x^{-5}+70x^{2}+28x^{3}-70x^{5}+70x^{8}$$ |
|  P1/P2:  |     $$1.42857x^{5}-1.42857x^{2}+0.571429+1.42857x^{-1}$$     |
|  P1%P2:  |             $$-8x^{-7}+8x^{-6}-3x^{-5}+4x^{-3}$$             |
| P1'(x):  | $$56x^{-8}-48x^{-7}+15x^{-6}-12x^{-4}+40x^{3}+20x^{4}-70x^{6}+100x^{9}$$ |
| P2'(x):  |                        $$-14x^{-3}$$                         |

| operator |                            result                            |
| :------: | :----------------------------------------------------------: |
|   P1:    |         $$-6x^{-6}-7x^{-4}+4x^{-2}+10x^{9}-9x^{10}$$         |
|   P2:    |       $$-12x^{-10}-3x^{-9}-3x^{-6}-10x^{-4}-5+5x^{5}$$       |
|  P1+P2:  | $$-12x^{-10}-3x^{-9}-9x^{-6}-17x^{-4}+4x^{-2}-5+5x^{5}+10x^{9}-9x^{10}$$ |
|  P1-P2:  | $$12x^{-10}+3x^{-9}-3x^{-6}+3x^{-4}+4x^{-2}+5-5x^{5}+10x^{9}-9x^{10}$$ |
|  P1*P2:  | $$72x^{-16}+18x^{-15}+84x^{-14}+21x^{-13}-30x^{-12}-12x^{-11}+81x^{-10}+58x^{-8}-10x^{-6}+35x^{-4}-20x^{-2}-150x^{-1}+78-8x^{1}-10x^{3}+27x^{4}-100x^{5}+90x^{6}-50x^{9}+45x^{10}+50x^{14}-45x^{15}$$ |
|  P1/P2:  |                    $$-1.8x^{-5}+2x^{-6}$$                    |
|  P1%P2:  | $$18x^{-6}-15.6x^{-5}-12.4x^{-4}+10x^{-2}-5.4x^{-1}+20-18x^{1}+10x^{4}-9x^{5}$$ |
| P1'(x):  |        $$36x^{-7}+28x^{-5}-8x^{-3}+90x^{8}-90x^{9}$$         |
| P2'(x):  |      $$120x^{-11}+27x^{-10}+18x^{-7}+40x^{-5}+25x^{4}$$      |

| operator |                            result                            |
| :------: | :----------------------------------------------------------: |
|   P1:    |            $$1x^{-9}-5x^{-4}+3x^{-2}+8+10x^{4}$$             |
|   P2:    |              $$8x^{-4}-7x^{-3}-2x^{4}+9x^{7}$$               |
|  P1+P2:  |     $$1x^{-9}+3x^{-4}-7x^{-3}+3x^{-2}+8+8x^{4}+9x^{7}$$      |
|  P1-P2:  |    $$1x^{-9}-13x^{-4}+7x^{-3}+3x^{-2}+8+12x^{4}-9x^{7}$$     |
|  P1*P2:  | $$8x^{-13}-7x^{-12}-40x^{-8}+35x^{-7}+24x^{-6}-23x^{-5}+64x^{-4}-56x^{-3}+9x^{-2}+90-70x^{1}-6x^{2}-45x^{3}-16x^{4}+27x^{5}+72x^{7}-20x^{8}+90x^{11}$$ |
|  P1/P2:  |                            $$0$$                             |
|  P1%P2:  |            $$1x^{-9}-5x^{-4}+3x^{-2}+8+10x^{4}$$             |
| P1'(x):  |            $$-9x^{-10}+20x^{-5}-6x^{-3}+40x^{3}$$            |
| P2'(x):  |            $$-32x^{-5}+21x^{-4}-8x^{3}+63x^{6}$$             |

### `double_output.txt`

| operator |                            result                            |
| :------: | :----------------------------------------------------------: |
|   P1:    | $$3.03249x^{-5}-3.86156x^{-4}-5.67531x^{-3}+2.93548x^{-2}+6.97777x^{-1}$$ |
|   P2:    |                  $$-3.40181x^{-8}+9.14185$$                  |
|  P1+P2:  | $$-3.40181x^{-8}+3.03249x^{-5}-3.86156x^{-4}-5.67531x^{-3}+2.93548x^{-2}+6.97777x^{-1}+9.14185$$ |
|  P1-P2:  | $$3.40181x^{-8}+3.03249x^{-5}-3.86156x^{-4}-5.67531x^{-3}+2.93548x^{-2}+6.97777x^{-1}-9.14185$$ |
|  P1*P2:  | $$-10.316x^{-13}+13.1363x^{-12}+19.3063x^{-11}-9.98595x^{-10}-23.7371x^{-9}+27.7226x^{-5}-35.3018x^{-4}-51.8828x^{-3}+26.8357x^{-2}+63.7897x^{-1}$$ |
|  P1/P2:  |                            $$0$$                             |
|  P1%P2:  | $$3.03249x^{-5}-3.86156x^{-4}-5.67531x^{-3}+2.93548x^{-2}+6.97777x^{-1}$$ |
| P1'(x):  | $$-15.1625x^{-6}+15.4463x^{-5}+17.0259x^{-4}-5.87096x^{-3}-6.97777x^{-2}$$ |
| P2'(x):  |                      $$27.2145x^{-9}$$                       |

| operator |                            result                            |
| :------: | :----------------------------------------------------------: |
|   P1:    | $$-2.71833x^{-9}+8.76529x^{-8}+9.75075x^{-6}-5.24406x^{-5}+8.06306x^{-4}+5.65737x^{-3}+12.0601x^{1}+7.38209x^{9}$$ |
|   P2:    |  $$-9.79227x^{-5}-5.75285x^{-2}+6.6524x^{-1}+3.50309x^{2}$$  |
|  P1+P2:  | $$-2.71833x^{-9}+8.76529x^{-8}+9.75075x^{-6}-15.0363x^{-5}+8.06306x^{-4}+5.65737x^{-3}-5.75285x^{-2}+6.6524x^{-1}+12.0601x^{1}+3.50309x^{2}+7.38209x^{9}$$ |
|  P1-P2:  | $$-2.71833x^{-9}+8.76529x^{-8}+9.75075x^{-6}+4.54821x^{-5}+8.06306x^{-4}+5.65737x^{-3}+5.75285x^{-2}-6.6524x^{-1}+12.0601x^{1}-3.50309x^{2}+7.38209x^{9}$$ |
|  P1*P2:  | $$26.6186x^{-14}-85.8321x^{-13}-79.8439x^{-11}-68.5088x^{-10}+51.3513x^{-10}-20.6454x^{-9}-111.493x^{-8}+55.3434x^{-7}+30.1683x^{-7}-4.18004x^{-6}-46.3856x^{-6}+21.0927x^{-5}+71.7928x^{-4}-118.096x^{-4}-18.3704x^{-3}+28.2456x^{-2}-49.5616x^{-1}+80.2285+42.2475x^{3}-72.2874x^{4}-42.4681x^{7}+49.1086x^{8}+25.8601x^{11}$$ |
|  P1/P2:  | $$2.10731x^{-2}-2.53542e-16x^{-2}-4.00181x^{-5}-5.07083e-16x^{-5}+3.46067x^{-6}+7.59948x^{-8}$$ |
|  P1%P2:  | $$-2.71833x^{-9}+8.76529x^{-8}+9.75075x^{-6}-5.24406x^{-5}+82.4792x^{-4}+5.65737x^{-3}+33.8879x^{-2}+4.53189x^{-1}-50.5548+31.9688x^{1}-25.4082x^{2}$$ |
| P1'(x):  | $$24.465x^{-10}-70.1223x^{-9}-58.5045x^{-7}+26.2203x^{-6}-32.2522x^{-5}-16.9721x^{-4}+12.0601+66.4388x^{8}$$ |
| P2'(x):  |  $$48.9614x^{-6}+11.5057x^{-3}-6.6524x^{-2}+7.00617x^{1}$$   |

| operator |                            result                            |
| :------: | :----------------------------------------------------------: |
|   P1:    | $$7.50529x^{-7}-3.25448x^{-3}+3.71585x^{1}-5.0813x^{4}+7.50522x^{5}-1.78977x^{7}$$ |
|   P2:    | $$0.50146x^{-9}-9.58805x^{-3}-2.61817-1.37046x^{3}+9.51107x^{4}-5.62968x^{5}-7.47023x^{7}+7.50054x^{10}$$ |
|  P1+P2:  | $$0.50146x^{-9}+7.50529x^{-7}-12.8425x^{-3}-2.61817+3.71585x^{1}-1.37046x^{3}+4.42978x^{4}+1.87555x^{5}-9.26x^{7}+7.50054x^{10}$$ |
|  P1-P2:  | $$-0.50146x^{-9}+7.50529x^{-7}+6.33357x^{-3}+2.61817+3.71585x^{1}+1.37046x^{3}-14.5924x^{4}+13.1349x^{5}+5.68047x^{7}-7.50054x^{10}$$ |
|  P1*P2:  | $$3.7636x^{-16}-1.63199x^{-12}-71.961x^{-10}+1.86335x^{-8}-19.6501x^{-7}+31.2041x^{-6}-2.54807x^{-5}-6.52211x^{-4}+79.9041x^{-3}-77.8801x^{-2}-0.897496x^{-2}-51.6061-40.6823x^{1}+48.7197x^{1}-53.6387x^{2}+56.2937x^{3}+19.2193x^{4}+30.4641x^{4}+15.6917x^{5}-20.919x^{6}-17.4467x^{7}+4.68592x^{7}-76.0869x^{8}-10.2856x^{8}+99.9888x^{9}-39.7992x^{10}+65.8294x^{11}-17.0226x^{11}-45.99x^{12}-24.7425x^{14}+56.2933x^{15}-13.4242x^{17}$$ |
|  P1/P2:  |                            $$0$$                             |
|  P1%P2:  | $$7.50529x^{-7}-3.25448x^{-3}+3.71585x^{1}-5.0813x^{4}+7.50522x^{5}-1.78977x^{7}$$ |
| P1'(x):  | $$-52.537x^{-8}+9.76344x^{-4}+3.71585-20.3252x^{3}+37.5261x^{4}-12.5284x^{6}$$ |
| P2'(x):  | $$-4.51314x^{-10}+28.7641x^{-4}-4.11137x^{2}+38.0443x^{3}-28.1484x^{4}-52.2916x^{6}+75.0054x^{9}$$ |

| operator |                            result                            |
| :------: | :----------------------------------------------------------: |
|   P1:    | $$7.17706x^{-9}+6.74593x^{-4}-8.66411+9.55522x^{6}+3.5018x^{7}+3.35999x^{8}$$ |
|   P2:    |                            $$0$$                             |
|  P1+P2:  | $$7.17706x^{-9}+6.74593x^{-4}-8.66411+9.55522x^{6}+3.5018x^{7}+3.35999x^{8}$$ |
|  P1-P2:  | $$7.17706x^{-9}+6.74593x^{-4}-8.66411+9.55522x^{6}+3.5018x^{7}+3.35999x^{8}$$ |
|  P1*P2:  |                            $$0$$                             |

| operator |                            result                            |
| :------: | :----------------------------------------------------------: |
|   P1:    |        $$-9.57278x^{-9}+9.36518x^{-4}+5.70397x^{1}$$         |
|   P2:    | $$-3.69914x^{-10}-9.38352x^{-8}+9.99445x^{-7}-4.66013x^{-5}-7.35025x^{-4}+5.91426x^{-2}+1.96492x^{-1}-6.38634x^{2}-3.56625x^{7}-3.98827x^{9}$$ |
|  P1+P2:  | $$-3.69914x^{-10}-9.57278x^{-9}-9.38352x^{-8}+9.99445x^{-7}-4.66013x^{-5}+2.01492x^{-4}+5.91426x^{-2}+1.96492x^{-1}+5.70397x^{1}-6.38634x^{2}-3.56625x^{7}-3.98827x^{9}$$ |
|  P1-P2:  | $$3.69914x^{-10}-9.57278x^{-9}+9.38352x^{-8}-9.99445x^{-7}+4.66013x^{-5}+16.7154x^{-4}-5.91426x^{-2}-1.96492x^{-1}+5.70397x^{1}+6.38634x^{2}+3.56625x^{7}+3.98827x^{9}$$ |
|  P1*P2:  | $$35.4111x^{-19}+89.8263x^{-17}-95.6747x^{-16}+9.96729x^{-14}+70.3624x^{-13}-87.8783x^{-12}+36.9839x^{-11}-18.8097x^{-10}-64.7428x^{-9}-68.8364x^{-8}+7.61176x^{-7}+112.396x^{-6}+18.4018x^{-5}-26.5812x^{-4}-41.9256x^{-3}-25.6703x^{-2}+33.7348x^{-1}+49.3867-69.8261x^{3}-37.3508x^{5}-20.3418x^{8}-22.749x^{10}$$ |
|  P1/P2:  |                            $$0$$                             |
|  P1%P2:  |        $$-9.57278x^{-9}+9.36518x^{-4}+5.70397x^{1}$$         |
| P1'(x):  |           $$86.155x^{-10}-37.4607x^{-5}+5.70397$$            |
| P2'(x):  | $$36.9914x^{-11}+75.0681x^{-9}-69.9612x^{-8}+23.3007x^{-6}+29.401x^{-5}-11.8285x^{-3}-1.96492x^{-2}-12.7727x^{1}-24.9638x^{6}-35.8944x^{8}$$ |

