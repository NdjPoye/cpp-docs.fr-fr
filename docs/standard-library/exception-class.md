---
title: exception, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- exception
dev_langs:
- C++
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24aa11044218257b3471e2d65fe652ca32d39196
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="exception-class"></a>exception, classe
La classe sert de classe de base pour toutes les exceptions levées par certaines expressions et par la bibliothèque C++ Standard.  
  
## <a name="syntax"></a>Syntaxe  
```  
class exception {
   public:
   exception();
   exception(const char* const &message);
   exception(const char* const &message, int);
   exception(const exception &right);
   exception& operator=(const exception &right);
   virtual ~exception();
   virtual const char *what() const;
   };  
``` 
## <a name="remarks"></a>Notes  
 Plus précisément, cette classe de base est la racine des classes d’exception standard définies dans [\<stdexcept>](../standard-library/stdexcept.md). La valeur de chaîne C retournée par `what` est non définie par le constructeur par défaut, mais peut être définie par les constructeurs pour certaines classes dérivées comme une chaîne C définie par l’implémentation. Aucune des fonctions membres ne lève d'exception.  
  
 Le paramètre `int` permet de spécifier qu’aucune mémoire ne doit être allouée. La valeur de `int` est ignorée.  
  
> [!NOTE]
>  Les constructeurs `exception(const char* const &message)` et `exception(const char* const &message, int)` sont des extensions Microsoft pour la bibliothèque C++ Standard.  
  
## <a name="example"></a>Exemple  
 Pour obtenir des exemples d’utilisation des classes d’exception standard qui héritent de la classe `exception`, consultez l’une des classes définies dans [\<stdexcept>](../standard-library/stdexcept.md).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<exception>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)



