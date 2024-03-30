For Sale Icon On - 

**SalesOn** = var selected = SELECTEDVALUE(Sale_Option[Type)
var _url = "https://drive.google.com/uc?export=view&id=1mcmb1peVHoaU5XL2bYXinZtW9sv2bNG4"
return IF(selected="1",_url)


-----------------------------------------------------------------------

For Units Icon On - 

**SalesOn** = var selected = SELECTEDVALUE(Sale_Option[Ty[e])
var _url = "https://drive.google.com/uc?export=view&id=1mcmb1peVHoaU5XL2bYXinZtW9sv2bNG4"
return IF(selected="2",_url)

-----------------------------------------------------------------------

**Seller Count **= CALCULATE([Sale_Units],ALL('amazon-fashion'[Category]))
= var val = CALCULATE(COUNT('amazon-fashion'[seller_id]),CONTAINSSTRING(Amazon[Status],"Delivered"))
Return val

-----------------------------------------------------------------------

**Filter Sale** = var selecting = SELECTEDVALUE(Sale_Option[Type])
var _units =SUM(Amazon[Qty])
var _sale = SUM(Amazon[Total_Ammount])
return IF(selecting="1",_sale,_units)

-----------------------------------------------------------------------

Color Orange - #FF9F10
Background Color - #F8F8F8
White Color -  #FFFFFF



Return_Units = var val= CALCULATE([Sale_Units],CONTAINSSTRING(Amazon[Status],"Return"))
return IF(val=BLANK(),0,val)


**Reviews** = var val = COUNT('amazon-fashion'[no__of_reviews])
return IF(ISBLANK(val),0)


**Sale_Ammount** = var val = SUM(Amazon[Total_Ammount])
return if(ISBLANK(val),0)


**Sale_Units** = var selecting = SELECTEDVALUE(Sale_Option[Type])
var _units =SUM(Amazon[Qty])
var _sale = SUM(Amazon[Total_Ammount])
return IF(selecting="1",_sale,_units)


**Sale_Option** =
 DataTable("Type", STRING,"Name”, STRING ,{{"1","Sales"},{"2","Units"}}) 


**Sale_Units** = var selecting = SELECTEDVALUE(Sale_Option[Type])
var _units =SUM(Amazon[Qty])
var _sale = SUM(Amazon[Total_Ammount])
return IF(selecting="1",_sale,_units)


**All_Sale** = CALCULATE([Sale_Units],ALL('amazon-fashion'[Category]))


**Order_Counts** = var val = CALCULATE(COUNT('amazon-fashion'[seller_id]),CONTAINSSTRING(Amazon[Status],"Delivered"))
return IF(val=BLANK(),"0",val)
