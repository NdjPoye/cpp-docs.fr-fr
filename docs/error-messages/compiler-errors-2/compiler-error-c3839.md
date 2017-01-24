---
title: "Erreur du compilateur C3839 | Microsoft Docs"
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
  - "C3839"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3839"
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3839
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible de changer l'alignement dans un type managé ou WinRT  
  
 L'alignement des variables dans les types managés ou Windows Runtime est contrôlé par le CLR ou Windows Runtime et ne peut pas être modifié avec [align](../../cpp/align-cpp.md).  
  
 L'exemple suivant génère l'erreur C3839 :  
  
```  
// C3839a.cpp  
// compile with: /clr  
ref class C  
{  
public:  
   __declspec(align(32)) int m_j; // C3839  
};  
  
int main()  
{  
}  
  
```