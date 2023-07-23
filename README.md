import math
from tkinter import *
from tkinter import messagebox
"""a. Yêu cầu 1 (CĐR L1; 4 điểm)
   - Tạo class đường thẳng gồm tọa độ 
   của 2 điểm trong mặt phẳng và 
   1 phương thức tính độ dài của đoạn thẳng."""
class duongthang():
    def __init__(self,x1,y1,x2,y2):
        self.x1=x1
        self.x2=x2
        self.y1=y1
        self.y2=y2
    def dodai(self):
        return math.sqrt((math.pow((self.x2-self.x1),2)+math.pow(self.y2-self.y1,2)))
"""
b. Yêu cầu 2 (CĐR L2; 4 điểm)
 - Nhập 1 list có 3 đoạn thẳng 
 (đoạn thẳng là các object tạo bởi 
 class trong yêu cầu 1. Khuyến khích tạo giao diện GUI)
 - Tính độ dài 3 đoạn thẳng vừa nhập 
-  Kiểm tra xem 3 cạnh vừa nhập có 
lập thành tam giác không? 
- Tìm đoạn thẳng dài nhất nhất."""

def nhap():
    xx1=x1.get()
    xx2=x2.get()
    xx3=x3.get()
    xx4=x14.get()
    xx5=x25.get()
    xx6=x36.get()

    yy1=y1.get()
    yy2=y2.get()
    yy3=y3.get()
    yy4=y14.get()
    yy5=y25.get()
    yy6=y36.get()
    obj1=duongthang(xx1,yy1,xx2,yy2)
    obj2=duongthang(xx3,yy3,xx4,yy4)
    obj3=duongthang(xx5,yy5,xx6,yy6)
    ds.append(obj1)
    ds.append(obj2)
    ds.append(obj3)
ds=[]  


ds1=[]
def tinhtoan():
    for i in range(len(ds)):
        ds1.append(ds[i].dodai())
    l1="độ dài 3 đoạn thẳng AB; CD; EF lần lượt là: "+str(ds1)
    hienthi.config(text=l1)
    hienthi.grid(column=1,row=12)

def kiemtra():
    if ds1[0]+ds1[1]>ds1[2] and ds1[1]+ds1[2]>ds1[0] and ds1[2]+ds1[2]>ds1[1]:
        la2="kết quả kiểm tra cho thấy 3 đoạn thẳng có thể tạo thành tam giác"
    else:
        la2="kết quả kiểm tra cho thấy 3 đoạn thẳng không thể tạo thành tam giác"
    nt.config(text=la2)
    nt.grid(column=1,row=13)
dsdd=[]
def timmax():
    dmax=max(ds1)
    la3="đoạn thẳng dài nhất là: "+str(dmax)
    hienthi2.config(text=la3)
    hienthi2.grid(column=1,row=14)
tung=Tk()
tung.title("bài tập 11")
tung.geometry("500x500")

#L1=Label(tung,text="nhập số đoạn thẳng").grid(column=0,row=0)
#l2=Button(tung,text="nhập",command=nhap()).grid(column=1,row=1)
L1=Label(tung,text="nhập thông tin đoạn thẳng").grid(column=1,row=0)
L12=Label(tung,text="tọa độ x").grid(column=1,row=1)
L21=Label(tung,text="tọa độ y").grid(column=2,row=1)

L2=Label(tung,text="nhập điểm A(x,y)").grid(column=0,row=2)
x1=DoubleVar()
n1=Entry(tung,textvariable=x1).grid(column=1,row=2)
y1=DoubleVar()
n2=Entry(tung,textvariable=y1).grid(column=2,row=2)

L2=Label(tung,text="nhập điểm B(x,y)").grid(column=0,row=3)
x2=DoubleVar()
n22=Entry(tung,textvariable=x2).grid(column=1,row=3)
y2=DoubleVar()
n32=Entry(tung,textvariable=y2).grid(column=2,row=3)

L2=Label(tung,text="nhập điểm C(x,y)").grid(column=0,row=4)
x3=DoubleVar()
n23=Entry(tung,textvariable=x3).grid(column=1,row=4)
y3=DoubleVar()
n33=Entry(tung,textvariable=y3).grid(column=2,row=4)


L2=Label(tung,text="nhập điểm D(x,y)").grid(column=0,row=5)
x14=DoubleVar()
n14=Entry(tung,textvariable=x14).grid(column=1,row=5)
y14=DoubleVar()
n24=Entry(tung,textvariable=y14).grid(column=2,row=5)

L25=Label(tung,text="nhập điểm E(x,y)").grid(column=0,row=6)
x25=DoubleVar()
n225=Entry(tung,textvariable=x25).grid(column=1,row=6)
y25=DoubleVar()
n325=Entry(tung,textvariable=y25).grid(column=2,row=6)

L26=Label(tung,text="nhập điểm F(x,y)").grid(column=0,row=7)
x36=DoubleVar()
n236=Entry(tung,textvariable=x36).grid(column=1,row=7)
y36=DoubleVar()
n336=Entry(tung,textvariable=y36).grid(column=2,row=7)

nhaptt=Button(tung,text="nhập",command=nhap).grid(column=1,row=8)
nhaptt2=Button(tung,text="tính toán",command=tinhtoan).grid(column=1,row=9)
nhaptt2=Button(tung,text="kiểm tra",command=kiemtra).grid(column=1,row=10)
nhaptt2=Button(tung,text="tìm đoạn dài nhất",command=timmax).grid(column=1,row=11)
nt=Label(tung)
hienthi=Label(tung)
hienthi2=Label(tung)
tung.mainloop()
