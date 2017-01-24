---
title: "Erreur du compilateur C2989 | Microsoft Docs"
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
  - "C2989"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2989"
ms.assetid: 936303d8-eb3b-4746-82ec-2f18020a6f64
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2989
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : le type de classe a déjà été déclaré comme type sans classe  
  
 Le générique ou le modèle de classe redéfinit une classe sans modèle ou sans générique.  Recherchez la présence d'un conflit dans les fichiers d'en\-tête.  
  
 Si vous utilisez les spécialisations partielles du modèle de classe, consultez l'article Q240866 de la Base de connaissances.  
  
 L'exemple suivant génère l'erreur C2989 :  
  
```  
// C2989.cpp  
// compile with: /c  
class C{};  
  
template <class T>  
class C{};  // C2989  
class C2{};  
```  
  
 L'erreur C2989 peut également se produire lors de l'utilisation de génériques :  
  
```  
// C2989b.cpp  
// compile with: /clr /c  
ref class GC1;  
  
generic <typename T> ref class GC1;   // C2989  
template <typename T> ref class GC2;  
  
generic <typename T> ref class GC2;   // C2989  
generic <typename T> ref class GCb;  
template <typename T> ref class GC2;  
generic <typename T> ref class GCc;  
```