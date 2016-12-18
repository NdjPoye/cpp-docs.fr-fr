---
title: "Prise en charge COM du compilateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compilateur cl.exe, prise en charge COM"
  - "COM, prise en charge par le compilateur"
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Prise en charge COM du compilateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Le compilateur Visual C\+\+ peut directement lire les bibliothèques de types COM \(Component Object Model\) et traduire le contenu en code source C\+\+ qui peut être inclus dans la compilation.  Les extensions de langage sont disponibles pour simplifier la programmation COM côté client.  
  
 À l'aide de la [directive de préprocesseur \#import](../preprocessor/hash-import-directive-cpp.md), le compilateur peut lire une bibliothèque de types et la convertir en un fichier d'en\-tête C\+\+ qui décrit les interfaces COM en tant que classes.  Un ensemble d'attributs `#import` est disponible pour permettre le contrôle utilisateur du contenu pour les fichiers d'en\-tête de la bibliothèque de types obtenus.  
  
 Vous pouvez utiliser l'attribut étendu [\_\_declspec](../cpp/declspec.md) [uuid](../cpp/uuid-cpp.md) pour assigner un identificateur global unique \(GUID\) à un objet COM.  Le mot clé [\_\_uuidof](../cpp/uuidof-operator.md) peut être utilisé pour récupérer un GUID associé à un objet COM.  Un autre attribut `__declspec`, [propriété](../cpp/property-cpp.md), peut être utilisé pour spécifier les méthodes **get** et **set** pour une donnée membre d'un objet COM.  
  
 Un ensemble de fonctions et de classes globales de prise en charge COM est fourni pour prendre en charge les types **VARIANT** et `BSTR`, pour implémenter les pointeurs intelligents et pour encapsuler l'objet d'erreur levé par `_com_raise_error` :  
  
-   [Fonctions globales COM du compilateur](../cpp/compiler-com-global-functions.md)  
  
-   [\_bstr\_t](../cpp/bstr-t-class.md)  
  
-   [\_com\_error](../cpp/com-error-class.md)  
  
-   [\_com\_ptr\_t](../cpp/com-ptr-t-class.md)  
  
-   [\_variant\_t](../cpp/variant-t-class.md)  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Classes du support COM du compilateur](../cpp/compiler-com-support-classes.md)   
 [Fonctions globales COM du compilateur](../cpp/compiler-com-global-functions.md)