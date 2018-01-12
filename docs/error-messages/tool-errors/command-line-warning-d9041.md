---
title: Avertissement de ligne de commande D9041 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: D9041
dev_langs: C++
helpviewer_keywords: D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 307d290bb525ee879f29853c6823d5b9565aba4b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-warning-d9041"></a>Avertissement de ligne de commande D9041
non valide 'valeur' pour '/ option' ; en supposant que 'value' ; Ajoutez ' /analyze ' aux options de ligne de commande lors de la spécification de cet avertissement  
  
 Un numéro d’avertissement de l’analyse du Code a été ajouté à la **/wd**, **/we**, **/wo**, ou **/wl** option de ligne de commande sans spécifier également le **/ analyze** option de ligne de commande. Pour corriger cette erreur, ajoutez le **/ analyze** option de ligne de commande, ou supprimez le numéro d’avertissement non valide approprié **Wn** option de ligne de commande.  
  
## <a name="example"></a>Exemple  
 L’exemple de ligne de commande suivant génère l’avertissement D9041 :  
  
```  
cl /EHsc /LD /wd6001 filename.cpp  
```  
  
 Pour résoudre l’avertissement, ajoutez le **/ analyze** option de ligne de commande. Si **/ analyze** est ne pas pris en charge sur votre version du compilateur, supprimez le numéro d’avertissement non valide à partir de la **/wd** option.  
  
## <a name="see-also"></a>Voir aussi  
 [Erreurs de ligne de commande D8000 à D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)