---
title: Erreur LNK1112 des outils Éditeur de liens | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1112
dev_langs:
- C++
helpviewer_keywords:
- LNK1112
ms.assetid: 425793d8-37e6-4072-9b6e-c3d4e9c12562
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd4af160607d75f036d25d21f5a95e753bddb3be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1112"></a>Erreur des outils Éditeur de liens LNK1112
le type d’ordinateur du module « type1 » est en conflit avec le type d’ordinateur cible « type2 »  
  
 Les fichiers objets spécifiés en entrée ont été compilés pour différents types d’ordinateurs.  
  
 Par exemple, si vous essayez de lier un fichier objet compilé avec **/clr** et un fichier objet compilé avec **/clr:pure** (type d’ordinateur CEE), l’éditeur de liens génère l’erreur LNK1112.  
  
 De même, si vous créez un module avec le compilateur [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] et un autre module avec le compilateur x86, et que vous tentez de les lier, l’éditeur de liens génère l’erreur LNK1112.  
  
 Une raison possible de cette erreur est que vous développez une application 64 bits, mais que vous n’avez pas installé un des compilateurs 64 bits de Visual C++. Dans ce cas, les configurations 64 bits ne sont pas disponibles. Pour résoudre ce problème, exécutez le programme d’installation pour Visual Studio et installez les composants C++ manquants.  
  
 Cette erreur peut également se produire si vous modifiez la **configuration de la solution active** dans **Configuration Manager** , puis que vous tentez de générer le projet avant de supprimer les fichiers projet intermédiaires. Pour résoudre cette erreur, sélectionnez **Régénérer la Solution** dans le menu **Générer** . Vous pouvez aussi sélectionner **Nettoyer la solution** dans le **Générer** , puis générer la solution.  
  
## <a name="see-also"></a>Voir aussi  
 [Erreurs et avertissements des outils Éditeur de liens](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)