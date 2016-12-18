---
title: "Erreur du compilateur C3675 | Microsoft Docs"
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
  - "C3675"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3675"
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3675
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : est réservé, car 'propriété' est défini  
  
 Lorsque vous déclarez une propriété simple, le compilateur génère les méthodes d'accesseur Get et Set, et ces noms sont présents dans la portée de votre programme.  Les noms générés par le compilateur sont constitués en ajoutant get\_ et set\_ au nom de la propriété.  Par conséquent, vous ne pouvez pas déclarer de fonction portant le même nom que les accesseurs générés par le compilateur.  
  
 Pour plus d'informations, consultez [property](../../windows/property-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3675 :  
  
```  
// C3675.cpp  
// compile with: /clr /c  
ref struct C {  
public:  
   property int Size;  
   int get_Size() { return 0; }   // C3675  
};  
```