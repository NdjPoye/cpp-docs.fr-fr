---
title: "Avertissement des outils &#201;diteur de liens LNK4247 | Microsoft Docs"
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
  - "LNK4247"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4247"
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement des outils &#201;diteur de liens LNK4247
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le point d'entrée 'nom\_fonction\_orné' a déjà un attribut de thread ; 'attribut' ignoré  
  
 Un point d'entrée, spécifié avec [\/ENTRY \(Symbole de point d'entrée\)](../../build/reference/entry-entry-point-symbol.md), possédait un attribut de thread, mais [\/CLRTHREADATTRIBUTE \(Définir l'attribut de thread CLR\)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md) était également spécifié, avec un modèle de thread différent.  
  
 L'éditeur de liens a ignoré la valeur spécifiée avec \/CLRTHREADATTRIBUTE.  
  
 Pour résoudre cet avertissement :  
  
-   Supprimez \/CLRTHREADATTRIBUTE de votre version.  
  
-   Supprimez l'attribut de votre fichier de code source.  
  
-   Supprimez à la fois l'attribut de la source et \/CLRTHREADATTRIBUTE de votre version, et acceptez le modèle de thread du CLR par défaut.  
  
-   Modifiez la valeur passée à \/CLRTHREADATTRIBUTE, de sorte qu'elle corresponde à l'attribut contenu dans la source.  
  
-   Modifiez l'attribut contenu dans la source, de sorte qu'il corresponde à la valeur passée à \/CLRTHREADATTRIBUTE.  
  
 L'exemple suivant génère l'erreur LNK4247  
  
```  
// LNK4247.cpp  
// compile with: /clr /c  
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console  
 [System::MTAThreadAttribute]  
void functionTitle (){}  
```