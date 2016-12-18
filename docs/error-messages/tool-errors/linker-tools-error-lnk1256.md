---
title: "Erreur des outils &#201;diteur de liens LNK1256 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "xml"
  - "LNK1256"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1256"
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK1256
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Échec de l'opération ALINK : raison  
  
 Une des raisons courantes de la survenue de l'erreur LNK1256 est l'existence d'un numéro de version incorrect pour un assembly.  La valeur 65 535 n'est pas autorisée, quelle que soit la partie du numéro de version de l'assembly.  La plage valide pour les versions d'assembly est comprise entre 0 et 65 534.  
  
 L'erreur LNK1256 peut aussi survenir si ALINK n'a pas trouvé le conteneur de clé nommé.  Supprimez le conteneur de clé et rajoutez\-le au fournisseur CSP de nom fort à l'aide de [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md).  
  
 L'erreur LNK1256 peut aussi être liée à une incompatibilité de version entre l'éditeur de liens et Alink.dll.  Une installation endommagée de Visual Studio peut en être la cause.  Utilisez **Programmes et fonctionnalités** dans le panneau de configuration Windows pour réparer ou réinstaller Visual Studio.  
  
 L'exemple suivant génère l'erreur LNK1256 :  
  
```  
// LNK1256.cpp  
// compile with: /clr /LD  
// LNK1256 expected  
[assembly:System::Reflection::AssemblyVersionAttribute("1.0.65535")];  
public class CMyClass {  
public:  
   int value;  
};  
```