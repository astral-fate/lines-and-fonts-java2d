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


الآن إذا أردنا تعديل عدة خصائص أخرى تخص النص، مثل سماكة النص، نستعمل الدالة Stroke حتى تحدد سُمك النص، كالتالي:


           Stroke NewStorke = new BasicStroke(200, BasicStorke.CAP_BUTT, BasicStroke.JOIN_BEVEL);
           
ثم لتعيين وتخصيص دالة السُمك التي عرفناها للتو، نستعمل دالة setStroke كالتالي:


          g2.setStroke(NewStroke);
          

بعد إذ، أن أردنا طباعة التالي، نلاحظ تغير السُمك كالتالي:


![image](https://user-images.githubusercontent.com/63984422/142727734-ba919727-daac-4aff-a381-70742f85226b.png)


أما إذا أردنا إضافة بعض الخصائص، والأساليب الأخرى، مثل أن نجعل النص يبدو مائلًا، فسنستعمل التحويلات الهندسية التي تعلمناها فيما سبق، بالأخص الShear حتى يُضفي على النص ميل


        AffineTransform newShear = new Affinetransform();
        
        newShare.shear(0,0.5);
        
        
        
ثم حتى نخصص هذا التحويل الهندسي، للنص الذي أردنا استعماله، نمرر متغيرات، للدالة setFont كالتالي


                  g2.setFont(NewFont.deriveFont(newShear));
                  
                  
بعد ذلك، حين نطبع النص، يكون كالتالي:        
        
![image](https://user-images.githubusercontent.com/63984422/142728161-3e804129-39e2-4377-9ec4-2c710674a184.png)


اما إذا أردنا التعامل مع النص باعتباره شكل، ذا متجهات، نستعمل الدالة Glyph Vector ونقوم بتعريفها كالتالي

                
                
                GlyphVector NewGlyph;
                
               
                
                
ثم نعين النص الذي نريد أن نجعله مُتجهًا، عن طريق استعمال دالة FontRenderContext 


              FontRenderContext NewContext = g2.getFontRenderContext();
              
              
ثم حتى نحول النص إلى شكل، نقوم بتعريف شكل جديد كالتالي 


             Shape GlyShape = NewGlyph.getOutline(50, 200);
             NewGlyph = createGlyphVector(NewContext, str);
             
             
            
ثم لطباعة النص الذي قمنا باعتباره كشكل: 


             
             g2.draw(GlyShape);







