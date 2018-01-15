---
title: -ALLOWBIND | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /allowbind
dev_langs: C++
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4cbd5c619b0a9e146adb9a8ec9117f59e01b89d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="allowbind"></a>/ALLOWBIND
Spécifie si une DLL peut être liée.  
  
```  
  
/ALLOWBIND[:NO]  
```  
  
## <a name="remarks"></a>Notes  
 Le **/ALLOWBIND** option définit un bit dans l’en-tête d’une DLL qui indique à Bind.exe que l’image est autorisée à être liée. Liaison permettent à une image de chargement plus rapide lorsque le chargeur ne doit pas nécessairement redéfinir et effectuer la correction de l’adresse pour chaque DLL référencée. Vous souhaiterez peut-être éviter une DLL soit liée si elle a été signée numériquement, la liaison invalide la signature. Liaison n’a aucun effet si la randomisation du format d’espace d’adresse (ASLR) est activée pour l’image à l’aide de **/DYNAMICBASE** sur les versions de Windows qui prennent en charge ASLR.  
  
 Utilisez **/ALLOWBIND : no** pour empêcher la liaison de la DLL Bind.exe.  
  
 Pour plus d’informations, consultez la [/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md) option de l’éditeur de liens.  
  
## <a name="see-also"></a>Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)