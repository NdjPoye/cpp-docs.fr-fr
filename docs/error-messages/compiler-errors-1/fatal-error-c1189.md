---
title: "Erreur irr&#233;cup&#233;rable C1189 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1189"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1189"
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Erreur irr&#233;cup&#233;rable C1189
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#error : message d'erreur défini par l'utilisateur  
  
 L'erreur C1189 est générée par la directive `#error`.  Le développeur qui code la directive spécifie le texte du message d'erreur.  Pour plus d'informations, consultez [\#error, directive](../../preprocessor/hash-error-directive-c-cpp.md).  
  
 L'exemple suivant génère l'erreur C1189 :  Dans l'exemple, le développeur émet un message d'erreur personnalisé parce que l'identificateur `_WIN32` n'est pas défini :  
  
```  
// C1189.cpp  
#undef _WIN32  
#if !defined(_WIN32)  
#error _WIN32 must be defined   // C1189  
#endif  
```  
  
 Cette erreur peut également survenir si vous générez un projet ATL à l'aide de l'option du compilateur **\/robust** MILD.  Utilisez le commutateur **\/robust** pour générer uniquement [!INCLUDE[win2kfamily](../../c-runtime-library/includes/win2kfamily_md.md)] et les versions ultérieures de windows.  Pour corriger l'erreur, utilisez l'une des procédures suivantes :  
  
-   Modifiez cette ligne dans le fichier dlldatax.c :  
  
```  
#define _WIN32_WINNT 0x0400   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
 en :  
  
```  
#define _WIN32_WINNT 0x0500   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
-   Utilisez la page de propriétés **Avancé** dans le dossier de la page de propriétés **MIDL** pour supprimer le commutateur **\/robust**, puis spécifier le commutateur **\/no\_robust**.  Pour plus d'informations, consultez [Pages de propriétés MIDL : Avancé](../../ide/midl-property-pages-advanced.md).  
  
## Voir aussi  
 [\#define, directive](../../preprocessor/hash-define-directive-c-cpp.md)