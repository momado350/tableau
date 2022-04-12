# tableau
1-Top Region:
IF {FIXED [Region] : SUM([Current Month Sales])} = {FIXED : MAX({FIXED [Region] : SUM([Current Month Sales])})} THEN [Region] END

2- Top Region sales:
IF {FIXED [Region] : SUM([Current Month Sales])} = {FIXED : MAX({FIXED [Region] : SUM([Current Month Sales])})} THEN [Current Month Sales] END

3- top shipping mode:
IF {FIXED [Ship Mode] : SUM([Current Month Sales])} = {FIXED : MAX({FIXED [Ship Mode] : SUM([Current Month Sales])})} THEN [Ship Mode] ELSE '' END

4- Average of category:
IF [Category] = "Furniture" THEN [Current Month Sales] END

5- current month discount:
IF MONTH([Order Date]) = [Select Month] THEN [Discount] END

6- discouont percentage change:
(SUM([Current Month Discount])-sum([Previous Month Sales  Discoount]))/(SUM([Previous Month Sales  Discoount]))*100

7- pervious month profits:
IF MONTH([Order Date]) =  [Select Month]-1 THEN [Profit] END

8- shiping time in days:
IF MONTH([Order Date]) = [Select Month] THEN [Ship Date] END - IF MONTH([Order Date]) = [Select Month] THEN [Order Date] END
