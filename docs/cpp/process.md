---
title: "processus | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Process"
  - "process_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec (mot clé) (C++), processus"
  - "process __declspec (mot clé)"
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# processus
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie que votre processus d'application managé doit comporter une seule copie d'une variable globale particulière, d'une variable membre static ou d'une variable locale static partagée par tous les domaines d'application du processus.  Il est principalement destiné à être utilisé lors de la compilation avec **\/clr:pure**, car sous **\/clr:pure**, les variables globales et static sont, par défaut, par domaine d'application.  Lors de la compilation avec **\/clr**, les variables globales et static sont, par défaut, par processus \(pas besoin d'utiliser `__declspec(process)`\).  
  
 Seules une variable globale, une variable membre static ou une variable locale static de type natif peuvent être marquées avec `__declspec(process)`.  
  
 Lors de la compilation avec **\/clr:pure**, les variables marquées par processus doivent également être déclarées en tant que `const`.  Cela garantit que les variables par processus ne sont pas modifiées dans un domaine d'application et qu'elle n'entraînent pas de résultats inattendus dans un autre domaine d'application.  L'utilisation principale prévue d'un `__declspec(process)` est de permettre l'initialisation au moment de la compilation d'une variable globale, d'une variable membre static ou d'une variable locale static sous **\/clr:pure**.  
  
 `process` est uniquement valide lors de la compilation avec [\/clr](../build/reference/clr-common-language-runtime-compilation.md) ou **\/clr:pure** et n'est pas valide lors de la compilation avec **\/clr:safe**.  
  
 Si vous souhaitez que chaque domaine d'application possède sa propre copie d'une variable globale, utilisez [appdomain](../cpp/appdomain.md).  
  
 Pour plus d'informations, consultez [Domaines d'application et Visual C\+\+](../dotnet/application-domains-and-visual-cpp.md).  
  
## Voir aussi  
 [\_\_declspec](../cpp/declspec.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)