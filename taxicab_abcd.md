x<sub>1</sub>³ + y<sub>1</sub>³ + x<sub>2</sub>³ + y<sub>2</sub>³ + x<sub>3</sub>³ + y<sub>3</sub>³ = r<sub>1</sub> * s<sub>1</sub> + r<sub>2</sub> * s<sub>2</sub> + r<sub>3</sub> * s<sub>3</sub>\
a = s<sub>1</sub> - s<sub>n</sub>\
b = r<sub>i</sub> - r<sub>1</sub>\
c = s<sub>i</sub> - s<sub>n</sub>\
d = r<sub>n</sub> - r<sub>1</sub>\
Ta = r<sub>1</sub> * s<sub>n</sub> + r<sub>1</sub> * (a + c) / 3 + s<sub>n</sub> * (b + d) / 3 + (b * c) / 3

 Ta( 3) == 87539319\
        == 603 * 145173\
        == 651 * 134469 => i = 2, a = 14322, b = 48, c = 3618, d = 66, (a + c) / 3 = 5980, (b + d) / 3 = 38, (b * c) / 3 = 57888\
        == 669 * 130851
 
 Ta( 4) == 6963472309248\
        == 21504 * 323822187\
        == 24384 * 285575472 => i = 2, a = 91334463, b = 2880, c = 53087748, d = 8448, (a + c) / 3 = 48140737, (b + d) / 3 = 3776, (b * c) / 3 = 50964238080\
        == 28272 * 246302784 => i = 3, a = 91334463, b = 6768, c = 13815060, d = 8448, (a + c) / 3 = 35049841, (b + d) / 3 = 5072, (b * c) / 3 = 31166775360\
        == 29952 * 232487724

Mod 3 = 0 for :\
 a + c = s<sub>1</sub> + s<sub>i</sub> - 2 * s<sub>n</sub>\
 b + d = r<sub>i</sub> + r<sub>n</sub> - 2 * r<sub>1</sub>\
 b * c = (r<sub>i</sub> - r<sub>1</sub>) * (s<sub>i</sub> - s<sub>n</sub>)
