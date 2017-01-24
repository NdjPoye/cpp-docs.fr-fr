---
title: "Erreur du compilateur C2061 | Microsoft Docs"
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
  - "C2061"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2061"
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2061
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur de syntaxe : identificateur 'identificateur'  
  
 Le compilateur a rencontré un identificateur là où il n'était pas attendu.  Vérifiez que cet `identifier` est déclaré avant de l'utiliser.  
  
 Un initialiseur peut être entre parenthèses.  Pour éviter ce problème, incluez le déclarateur entre parenthèses ou transformez\-le en `typedef`.  
  
 Cette erreur peut également se produire lorsque le compilateur détecte une expression comme un argument template de classe ; utilisez [typename](../../cpp/typename.md) pour indiquer au compilateur qu'il s'agit d'un type.  
  
 L'exemple suivant génère l'erreur C2061 :  
  
```  
// C2061.cpp  
// compile with: /c  
template < A a >   // C2061  
// try the following line instead  
// template < typename b >  
class c{};  
```  
  
 L'erreur C2061 peut se produire si vous passez un nom d'instance à [typeid](../../windows/typeid-cpp-component-extensions.md):  
  
```  
// C2061b.cpp  
// compile with: /clr  
ref struct G {  
   int i;  
};  
  
int main() {  
   G ^ pG = gcnew G;  
   System::Type ^ pType = typeid<pG>;   // C2061  
   System::Type ^ pType2 = typeid<G>;   // OK  
}  
```