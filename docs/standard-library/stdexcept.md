---
title: "&lt; stdexcept &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.<stdexcept>"
  - "std::<stdexcept>"
  - "<stdexcept>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "stdexcept (en-tête)"
ms.assetid: 495c10b1-1e60-4514-9f8f-7fda11a2f522
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt; stdexcept &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit plusieurs classes standard utilisées pour les rapports d'exceptions. Les classes forment une hiérarchie de dérivation dérivée d’une classe [exception](../standard-library/exception-class1.md) et incluent deux types généraux d’exceptions : erreurs de logiques et les erreurs d’exécution. Les erreurs logiques sont dues à des erreurs de programmeur. Elles dérivent de la classe de base logic_error et incluent :  
  
-   `domain_error`  
  
-   `invalid_argument`  
  
-   `length_error`  
  
-   `out_of_range`  
  
 Les erreurs d'exécution sont dues à des erreurs dans les fonctions de bibliothèque ou dans le système d'exécution. elles dérivent de la classe de base runtime_error et incluent :  
  
-   `overflow_error`  
  
-   `range_error`  
  
-   `underflow_error`  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[domain_error, classe](../standard-library/domain-error-class.md)|Classe qui sert de classe de base pour toutes les exceptions levées pour signaler une erreur de domaine.|  
|[invalid_argument, classe](../standard-library/invalid-argument-class.md)|Classe qui sert de classe de base pour toutes les exceptions levées pour signaler un argument non valide.|  
|[length_error, classe](../standard-library/length-error-class.md)|Classe qui sert de classe de base pour toutes les exceptions levées pour signaler une tentative de génération d'un objet trop long pour être spécifié.|  
|[logic_error, classe](../standard-library/logic-error-class.md)|Classe qui sert de classe de base pour toutes les exceptions levées pour signaler des erreurs normalement détectables avant l'exécution du programme, telles que les violations de conditions préalables logiques.|  
|[out_of_range, classe](../standard-library/out-of-range-class.md)|Classe qui sert de classe de base pour toutes les exceptions levées pour signaler un argument qui est en dehors de sa plage valide.|  
|[overflow_error, classe](../standard-library/overflow-error-class.md)|Classe qui sert de classe de base pour toutes les exceptions levées pour signaler un dépassement de capacité arithmétique positif.|  
|[range_error, classe](../standard-library/range-error-class.md)|Classe qui sert de classe de base pour toutes les exceptions levées pour signaler une erreur de plage.|  
|[runtime_error, classe](../standard-library/runtime-error-class.md)|Classe qui sert de classe de base pour toutes les exceptions levées pour signaler des erreurs normalement détectables uniquement durant l'exécution du programme.|  
|[underflow_error, classe](../standard-library/underflow-error-class.md)|Classe qui sert de classe de base pour toutes les exceptions levées pour signaler un dépassement de capacité arithmétique négatif.|  
  
## <a name="see-also"></a>Voir aussi  
 [Référence de fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

