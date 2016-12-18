---
title: "Comment&#160;: impl&#233;menter une architecture de composants plug-in &#224; l&#39;aide de la r&#233;flexion (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "plug-ins (C++)"
  - "réflection (C++), plug-ins"
ms.assetid: 4f31e42b-78d1-48b9-8fdc-f28c75e8e77e
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: impl&#233;menter une architecture de composants plug-in &#224; l&#39;aide de la r&#233;flexion (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les exemples de code suivants montrent l'utilisation de la réflexion pour implémenter une architecture de « plug\-in » simple.  La première liste est l'application, et la seconde est le plug\-in.  L'application est un formulaire de documents multiples qui se remplit automatiquement à l'aide de toutes les classes basées sur un formulaire situé dans la DLL de plug\-in fournie comme un argument de ligne de commande.  
  
 L'application essaie de charger l'assembly fourni à l'aide de la méthode <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>.  S'il réussit, les types contenus dans l'assembly sont énumérés à l'aide de la méthode <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName>.  Ensuite, la compatibilité de chaque type est vérifiée à l'aide de la méthode <xref:System.Type.IsAssignableFrom%2A?displayProperty=fullName>.  Dans cet exemple, les classes détectées dans l'assembly fourni doivent être dérivées de la classe <xref:System.Windows.Forms.Form> pour être considérées en tant que plug\-in.  
  
 Les classes compatibles sont alors instanciées avec la méthode <xref:System.Activator.CreateInstance%2A?displayProperty=fullName> qui accepte <xref:System.Type> comme argument et retourne un pointeur vers une nouvelle instance.  Ensuite, chaque nouvelle instance est jointe au formulaire et affichée.  
  
 Notez que la méthode <xref:System.Reflection.Assembly.Load%2A> n'accepte pas les noms d'assemblys comprenant l'extension de fichier.  La fonction principale de l'application tronque toute extension fournie ; l'exemple de code suivant fonctionne donc dans l'un et l'autre cas.  
  
## Exemple  
 Le code suivant définit l'application qui accepte des plug\-ins.  Un nom d'assembly doit être fourni comme premier argument.  Cet assembly doit contenir au moins un type dérivé <xref:System.Windows.Forms.Form> public.  
  
```  
// plugin_application.cpp  
// compile with: /clr /c  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
using namespace System::Reflection;  
  
ref class PluggableForm : public Form  {  
public:  
   PluggableForm() {}  
   PluggableForm(Assembly^ plugAssembly) {  
      Text = "plug-in example";  
      Size = Drawing::Size(400, 400);  
      IsMdiContainer = true;  
  
      array<Type^>^ types = plugAssembly->GetTypes( );  
      Type^ formType = Form::typeid;  
  
      for (int i = 0 ; i < types->Length ; i++) {  
         if (formType->IsAssignableFrom(types[i])) {  
            // Create an instance given the type description.  
            Form^ f = dynamic_cast<Form^> (Activator::CreateInstance(types[i]));  
            if (f) {  
               f->Text = types[i]->ToString();  
               f->MdiParent = this;  
               f->Show();  
            }  
         }  
      }  
   }  
};  
  
int main() {  
   Assembly^ a = Assembly::LoadFrom("plugin_application.exe");  
   Application::Run(gcnew PluggableForm(a));  
}  
```  
  
## Exemple  
 Le code suivant définit trois classes dérivées de <xref:System.Windows.Forms.Form>.  Lorsque le nom d'assembly résultant est passé au fichier exécutable dans la liste précédente, chacune de ces trois classes est découverte et instanciée, en dépit du fait qu'elles étaient toutes inconnues de l'application hôte au moment de la compilation.  
  
```  
// plugin_assembly.cpp  
// compile with: /clr /LD  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
using namespace System::Reflection;  
using namespace System::Drawing;  
  
public ref class BlueForm : public Form {  
public:  
   BlueForm() {  
      BackColor = Color::Blue;  
   }  
};  
  
public ref class CircleForm : public Form {  
protected:  
   virtual void OnPaint(PaintEventArgs^ args) override {  
      args->Graphics->FillEllipse(Brushes::Green, ClientRectangle);  
   }  
};  
  
public ref class StarburstForm : public Form {  
public:  
   StarburstForm(){  
      BackColor = Color::Black;  
   }  
protected:  
   virtual void OnPaint(PaintEventArgs^ args) override {  
      Pen^ p = gcnew Pen(Color::Red, 2);  
      Random^ r = gcnew Random( );  
      Int32 w = ClientSize.Width;  
      Int32 h = ClientSize.Height;  
      for (int i=0; i<100; i++) {  
         float x1 = w / 2;  
         float y1 = h / 2;  
         float x2 = r->Next(w);  
         float y2 = r->Next(h);  
         args->Graphics->DrawLine(p, x1, y1, x2, y2);  
      }  
   }  
};  
```  
  
## Voir aussi  
 [Réflexion](../dotnet/reflection-cpp-cli.md)