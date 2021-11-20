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
       
       
       Font NewFont = new Font("Strief", Font.BOLD, 20);
