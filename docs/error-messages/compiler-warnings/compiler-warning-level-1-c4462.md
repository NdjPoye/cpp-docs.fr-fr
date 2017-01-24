---
title: "Avertissement du compilateur (niveau 1) C4462 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4462"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4462"
ms.assetid: 4e20aca4-293e-4c75-a83d-961c27ab7840
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4462
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible de déterminer le GUID du type.Le programme risque d'échouer au moment de l'exécution.  
  
 L'avertissement C4462 se produit dans une application ou un composant Windows Runtime lorsqu'un `TypedEventHandler` public a parmi l'un de ses paramètres de type une référence à une classe englobante.  
  
 **Ce genre de code génère l'avertissement :**  
  
```  
namespace N  
{  
       public ref struct EventArgs sealed {};  
       public ref struct R sealed  
       {  
              R() {}  
              event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;  
       };  
}  
  
[Platform::MTAThread]  
int main()  
{  
     auto x = ref new N::R();  
}  
  
```  
  
 **Pour corriger l'erreur :**  
  
 Il existe deux solutions pour contourner l'erreur.  La première solution, comme le montre l'exemple suivant, consiste à donner à l'événement une accessibilité interne afin qu'il soit accessible au code du même exécutable mais pas au code des autres composants Windows Runtime.  
  
```  
  
internal:  
event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;  
  
```  
  
 Si l'événement doit être public, vous pouvez utiliser l'autre solution, qui consiste à l'exposer via une interface par défaut :  
  
```  
  
ref struct R;  
public interface struct IR { event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e; };  
  
public ref struct R sealed : [Windows::Foundation::Metadata::Default] IR  
{  
    R() {}  
    virtual event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;  
};  
  
```  
  
 Un GUID de type `Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^` est utilisé uniquement lorsque le type est accessible à partir d'un autre composant.  La première solution fonctionne, car l'événement n'est accessible que dans son propre composant \(une fois la solution appliquée\).  Sinon, le compilateur doit partir du cas le plus défavorable et émettre l'avertissement.