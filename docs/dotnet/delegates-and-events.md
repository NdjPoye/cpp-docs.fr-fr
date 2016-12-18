---
title: "D&#233;l&#233;gu&#233;s et &#233;v&#233;nements | Microsoft Docs"
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
  - "__delegate (mot clé)"
  - "__event (mot clé C++)"
  - "delegate (mot clé C++)"
  - "délégués (C++), mise à niveau à partir des extensions managées pour C++"
  - "event (mot clé C++)"
  - "événements (C++), mise à niveau à partir des extensions managées pour C++"
ms.assetid: 3505c626-7e5f-4492-a947-0e2248f7b84a
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;l&#233;gu&#233;s et &#233;v&#233;nements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La façon de déclarer des délégués et des événements a été modifiée entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 Le trait de soulignement double n'est plus nécessaire, comme illustré dans l'exemple ci\-après.  Voici un exemple de code dans les Extensions managées :  
  
```  
__delegate void ClickEventHandler(int, double);  
__delegate void DblClickEventHandler(String*);  
  
__gc class EventSource {  
   __event ClickEventHandler* OnClick;    
   __event DblClickEventHandler* OnDblClick;    
};  
```  
  
 Le même code dans la nouvelle syntaxe se présente ainsi :  
  
```  
delegate void ClickEventHandler( int, double );  
delegate void DblClickEventHandler( String^ );  
  
ref class EventSource {  
   event ClickEventHandler^ OnClick;   
   event DblClickEventHandler^ OnDblClick;   
};  
```  
  
 Les événements \(et les délégués\) sont des types référence, ce que la présence du chapeau \(`^`\) illustre clairement dans la nouvelle syntaxe.  Les événements prennent en charge à la fois une syntaxe de déclaration explicite et la forme simple illustrée dans le code précédent.  Sous forme explicite, l'utilisateur spécifie les méthodes `add`, `raise` et `remove` associées à l'événement. \(Seules les méthodes `add` et `remove` sont requises ; la méthode `raise` est facultative\).  
  
 Sous les Extensions managées, si vous fournissez ces méthodes, vous ne fournissez pas également une déclaration d'événement explicite, mais vous devez choisir un nom pour l'événement qui n'est pas présent.  Chaque méthode est spécifiée sous la forme `add_EventName`, `raise_EventName` et `remove_EventName`, comme dans l'exemple suivant emprunté à la spécification d'Extensions managées :  
  
```  
// explicit implementations of add, remove, raise  
public __delegate void f(int);  
public __gc struct E {  
   f* _E;  
public:  
   E() { _E = 0; }  
  
   __event void add_E1(f* d) { _E += d; }  
  
   static void Go() {  
      E* pE = new E;  
      pE->E1 += new f(pE, &E::handler);  
      pE->E1(17);   
      pE->E1 -= new f(pE, &E::handler);  
      pE->E1(17);   
   }  
  
private:  
   __event void raise_E1(int i) {  
      if (_E)  
         _E(i);  
   }  
  
protected:  
   __event void remove_E1(f* d) {  
      _E -= d;  
   }  
};  
```  
  
 La nouvelle syntaxe simplifie la déclaration, comme le montre la traduction ci\-après.  Un événement spécifie les deux ou trois méthodes entourées par des accolades et placées immédiatement après la déclaration de l'événement et de son type délégué associé, comme illustré ci\-après :  
  
```  
public delegate void f( int );  
public ref struct E {  
private:  
   f^ _E; // delegates are also reference types  
  
public:  
   E() {  // note the replacement of 0 with nullptr!  
      _E = nullptr;   
   }  
  
   // the new aggregate syntax of an explicit event declaration  
   event f^ E1 {  
   public:  
      void add( f^ d ) {  
         _E += d;  
      }  
  
   protected:  
      void remove( f^ d ) {  
         _E -= d;  
      }  
  
   private:  
      void raise( int i ) {  
         if ( _E )  
            _E( i );  
      }  
   }  
  
   static void Go() {  
      E^ pE = gcnew E;  
      pE->E1 += gcnew f( pE, &E::handler );  
      pE->E1( 17 );   
      pE->E1 -= gcnew f( pE, &E::handler );  
      pE->E1( 17 );   
   }  
};  
```  
  
## Voir aussi  
 [Déclarations de membre dans une classe ou interface \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [délégué](../windows/delegate-cpp-component-extensions.md)   
 [event](../windows/event-cpp-component-extensions.md)