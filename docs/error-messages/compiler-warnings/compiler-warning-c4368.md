---
title: "Avertissement du compilateur C4368 | Microsoft Docs"
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
  - "C4368"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4368"
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur C4368
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible de définir 'membre' comme membre de 'type' managé : les types mixtes ne sont pas pris en charge  
  
 Vous ne pouvez pas incorporer de donnée membre native dans un type CLR.  
  
 Toutefois, vous pouvez déclarer un pointeur vers un type natif et contrôler sa durée de vie dans le constructeur, le destructeur et le finaliseur de votre classe managée.  Pour plus d'informations, consultez [Destructeurs et finaliseurs](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
 Cet avertissement est toujours émis en tant qu'erreur.  Utilisez le pragma [warning](../../preprocessor/warning.md) pour désactiver l'erreur C4368.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4368 :  
  
```  
// C4368.cpp  
// compile with: /clr /c  
struct N {};  
ref struct O {};  
ref struct R {  
    R() : m_p( new N ) {}  
    ~R() { delete m_p; }  
  
   property N prop;   // C4368  
   int i[10];   // C4368  
  
   property O ^ prop2;   // OK  
   N * m_p;   // OK  
};  
```