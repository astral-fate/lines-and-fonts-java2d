# lines-and-fonts-java2d

لإضافة النصوص في جافا ثنائية الأبعاد، علينا أولًا أن نستورد هذه المكتبات من مكتبة جافا عن طريق كتابة النص البرمجي التالي:

         import java.awt.FontRenderContext;
         
         
بعد هذا يمكننا بسهولة تعريف نص جديد، بصيغة String وتعين له بعض الخصائص وأساليب الخط 


        String sr = new String ("this is text sample");
        
        
حين نريدالآن تعين أسلوب خط جديد للنص الذي عيناه للتو، سنقوم بتعريف دالة الـ Font كالتالي
عن طريق تحديد بعض الخصائص منها:



الحجم - Size



 والنوع سواء أكان BOLD, OR ITALIC
 
 
 
ومن خلال تحديد الخصائص، أي اسم الخط، مثل Serif, SansSerif, Monospaced, Dialog, and DialogInput 
       
       
       Font NewFont = new Font("Serif", Font.BOLD, 80);
       
       
       
لتخصيص اسلوب الخط الذي عيناه للتو، يتوجب علينا استعمال دالة setFont حتى نخصص أسلوب الخط


      g2.setFont(NewFont);
       
       
لطباعة الشكل التالي، نكتب النص البرمجي التالي، مع تحديدنا لأبعاده من نقطة x و y

      g2.drawString(sr, 200,200);
      
      
ستكون المخرجات كالتالي:


![image](https://user-images.githubusercontent.com/63984422/142727371-2034a971-37b7-4448-834c-21d8bf5595d2.png)



