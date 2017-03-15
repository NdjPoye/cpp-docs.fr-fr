---
title: "Comment&#160;: d&#233;finir et installer un gestionnaire d&#39;exceptions global | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gestionnaires, globaux"
ms.assetid: dd88a812-3bc7-4ce8-8283-4b674c246534
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Comment&#160;: d&#233;finir et installer un gestionnaire d&#39;exceptions global
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant illustre comment les exceptions non gérées peuvent être capturées.  Le formulaire d'exemple contient un bouton qui, une fois appuyé, effectue une référence nulle, provoquant une exception à lever.  Cette fonctionnalité représente une erreur classique de code.  L'exception résultante est interceptée par le gestionnaire d'exceptions installé par la fonction principale.  
  
 Cela est possible en liant un délégué à l'événement de <xref:System.Windows.Forms.Application.ThreadException>.  Dans ce cas, les exceptions suivantes sont ensuite envoyées à la méthode de `App::OnUnhandled`.  
  
## Exemple  
  
```  
// global_exception_handler.cpp  
// compile with: /clr  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Threading;  
using namespace System::Drawing;  
using namespace System::Windows::Forms;  
  
ref class MyForm : public Form  
{  
   Button^ b;  
public:  
   MyForm( )  
   {  
      b = gcnew Button( );  
      b->Text = "Do Null Access";  
      b->Size = Drawing::Size(150, 30);  
      b->Click += gcnew EventHandler(this, &MyForm::OnClick);  
      Controls->Add(b);  
   }  
   void OnClick(Object^ sender, EventArgs^ args)   
   {  
      // do something illegal, like call through a null pointer...  
      Object^ o = nullptr;  
      o->ToString( );        
   }  
};  
  
ref class App  
{  
public:  
   static void OnUnhandled(Object^ sender, ThreadExceptionEventArgs^ e)  
   {  
      MessageBox::Show(e->Exception->Message, "Global Exeception");  
      Application::ExitThread( );  
   }  
};  
  
int main()  
{  
   Application::ThreadException += gcnew   
      ThreadExceptionEventHandler(App::OnUnhandled);  
  
   MyForm^ form = gcnew MyForm( );  
   Application::Run(form);  
}  
```  
  
## Voir aussi  
 [Exception Handling](../windows/exception-handling-cpp-component-extensions.md)