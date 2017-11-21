---
title: once_flag, structure | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: mutex/std::once_flag
dev_langs: C++
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dded28d846ded9472ff9cee140366e5bab18b49a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="onceflag-structure"></a>once_flag, structure
Représente un `struct` utilisé avec la fonction de modèle [call_once](../standard-library/mutex-functions.md#call_once) pour garantir que le code d’initialisation est appelé une seule fois, même en présence de plusieurs threads d’exécution.  
  
## <a name="syntax"></a>Syntaxe  
  
struct once_flag { constexpr once_flag() noexcept; once_flag(const once_flag&); once_flag& operator=(const once_flag&); };  
  
## <a name="remarks"></a>Remarques  
 Le `once_flag` `struct` possède uniquement un constructeur par défaut.  
  
 Les objets de type `once_flag` peuvent être créés, mais ils ne peuvent pas être copiés.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<mutex >  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)



