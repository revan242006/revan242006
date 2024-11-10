from tkinter import*

window=Tk()

window.geometry("200x350+100+150")
window.configure(bg="white")

def tombol_klik(item):
    global ekspresi
    ekspresi = ekspresi + str(item)
    input_text.set(ekspresi)

def tombol_hapus():
    global ekspresi
    ekspresi =""
    input_text.set("")
    
ekspresi=""
input_text=StringVar()

def tombol_samadengan():
	global ekspresi
	hasil= str(eval(ekspresi))
	input_text.set(hasil)
	ekspresi=""
	
def tombol_negasi():
    global ekspresi
    if ekspresi:
        try:
            angka_terakhir = eval(ekspresi)
            ekspresi = str(-angka_terakhir)
            input_text.set(ekspresi)
        except Exception as e:
            input_text.set("Error")
            ekspresi = ""
            
def tombol_hasil():
        try:
            hasil = str(eval(ekspresi.replace('%', '/100')))
            input_teks.set(hasil)
            ekspresi = ""
        except:
            input_teks.set("Error")
            ekspresi = ""
            
ekspresi=""
input_text=StringVar()
    
frame1=Frame(window, bg="black",width=500,height=300)
frame1. pack(padx=0, pady=0)

label=Label(frame1, text="kalkulator,revan",width=40,anchor="w",font=("Arial",10))
label.pack(padx=0, pady=0)

label2=Label(frame1, text="Muhammad Revan XII PPLG 1",anchor="e",width=20,font=("Arial",15), textvariable=input_text)
label2.pack(padx=20, pady=20)

frame2=Frame(window, bg="black",width=600,height=0)
frame2.pack(pady=10,padx=0)

button=Button(frame2, text="AC",width=6,height=2,bg="black", fg="white",command=lambda:tombol_hapus())
button.grid(row=0,column=0,pady=0,padx =0)

button=Button(frame2, text="+/-",width=6,height=2,bg="black", fg="white",command=lambda:tombol_negasi())
button.grid(row=0,column=1,pady=0,padx =0)

button=Button(frame2, text="%",width=6,height=2,bg="black", fg="white",command=lambda:tombol_klik("%"))
button.grid(row=0,column=2,pady=0,padx =0)

button3=Button(frame2, text="/",width=6,height=2, bg="orange",fg="white",command=lambda:tombol_klik("/"))
button3.grid(row=0,column=3,pady=0,padx=0)

button4=Button(frame2, text="*",bg="orange",fg="white",width=6,height=2,command=lambda:tombol_klik("*"))
button4.grid(row=1,column=3,pady=0,padx=0)

button8=Button(frame2, text="+",bg="orange",fg="white",width=6,height=2,command=lambda:tombol_klik("+"))
button8.grid(row=3,column=3,pady=0,padx=0)

button5=Button(frame2, text="7",bg="gray",fg="white",width=6,height=2,command=lambda:tombol_klik("7"))
button5.grid(row=1,column=0,columnspan=1,pady=0,padx=0)

button6=Button(frame2, text="8",bg="gray",fg="white",width=6,height=2,command=lambda:tombol_klik("8"))
button6.grid(row=1,column=1,pady=0,padx=0)

button7=Button(frame2, text="9",bg="gray",fg="white",width=6,height=2,command=lambda:tombol_klik("9"))
button7.grid(row=1,column=2,pady=0,padx=0)
 
button9=Button(frame2, text="4",bg="gray",fg="white",width=6,height=2,command=lambda:tombol_klik("4"))
button9.grid(row=2,column=0,pady=0,padx=0)

button10=Button(frame2, text="5",bg="gray",fg="white",width=6,height=2,command=lambda:tombol_klik("5"))
button10.grid(row=2,column=1,pady=0,padx=0)

button11=Button(frame2, text="6",bg="gray",fg="white",width=6,height=2,command=lambda:tombol_klik("6"))
button11.grid(row=2,column=2,pady=0,padx=0)

button12=Button(frame2, text="-",bg="orange",fg="white",width=6,height=2,command=lambda:tombol_klik("-"))
button12.grid(row=2,column=3,pady=0,padx=0)

button13=Button(frame2, text="1",width=6,height=2,bg="gray",fg="white",command=lambda:tombol_klik("1"))
button13.grid(row=3,column=0,pady=0,padx=0)

button14=Button(frame2, text="2",bg="gray",fg="white",width=6,height=2,command=lambda:tombol_klik("2"))
button14.grid(row=3,column=1,pady=0,padx=0)

button15=Button(frame2, text="3",bg="gray",fg="white",width=6,height=2,command=lambda:tombol_klik("3"))
button15.grid(row=3,column=2,pady=0,padx=0)

button16=Button(frame2, text="=",command=lambda:tombol_samadengan(),height=2,width=6,bg="orange",fg="white")
button16.grid(row=4,column=3,rowspan=3,pady=0,padx=0)
 
button17=Button(frame2, text="0", bg="gray",fg="white",width=16,height=2,command=lambda:tombol_klik("0"))
button17.grid(row=4,column=0,columnspan=2,pady=0,padx=0)

button19=Button(frame2, text=".",bg="gray",fg="white",width=6,height=2,command=lambda:tombol_klik("."))
button19.grid(row=4,column=2,columnspan=1,pady=0,padx=0)

window.mainloop()
