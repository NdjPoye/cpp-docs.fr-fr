---
title: "Implémentation d’Interface Assistant | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.impl.interface.overview
dev_langs: C++
helpviewer_keywords: Implement Interface Wizard [C++]
ms.assetid: 947c329e-0815-4ca7-835e-c41dfeb75f9e
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d224546eb8bb06421c2e84206e1f4d4dc77f9668
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="implement-interface-wizard"></a>Assistant Implémentation d'interface
Cet Assistant implémente une interface pour un objet COM. Les implémentations de nombreuses interfaces sont incluses dans les bibliothèques COM disponibles avec Visual Studio et Windows. Une implémentation d’interface est associée à un objet lorsqu’une instance de cet objet est créée, et il fournit les services qui offre de l’objet.  
  
 Pour en savoir plus sur les interfaces et les implémentations, consultez [Interfaces et implémentations d’Interface](http://msdn.microsoft.com/library/windows/desktop/ms694356) dans le Kit de développement logiciel Windows.  
  
 **Implémenter l’interface**  
 Spécifie l’emplacement de la bibliothèque de types à partir de laquelle l’interface est créée.  
  
|Option|Description|  
|------------|-----------------|  
|**Projet**|La bibliothèque de types fait partie du projet.|  
|**Registry**|La bibliothèque de types est enregistrée dans le système. Bibliothèques de types inscrits sont répertoriés dans **bibliothèques de types disponibles**.|  
|**Fichier**|La bibliothèque de types n’est pas nécessairement inscrite dans le système, mais est contenue dans un fichier. Vous devez fournir l’emplacement du fichier dans **emplacement**.|  
  
 **Bibliothèques de types disponibles**  
 Affiche les bibliothèques de types disponibles contenant les définitions d’interface que vous pouvez implémenter. Si vous cliquez sur **fichier** sous **implémenter l’interface**, cette case n’est pas disponible pour modification.  
  
 **Emplacement**  
 Affiche l’emplacement de la bibliothèque de types actuellement sélectionnée dans le **bibliothèques de types disponibles** liste. Si vous avez sélectionné **fichier** sous **implémenter l’interface**, cliquez sur le bouton de sélection pour rechercher un fichier contenant la bibliothèque de types à utiliser.  
  
 **Interfaces**  
 Affiche les interfaces dont les définitions sont contenues dans la bibliothèque de types actuellement sélectionnée dans le **bibliothèques de types disponibles** boîte.  
  
> [!NOTE]
>  Les interfaces qui ont le même nom que celles déjà implémentées par l’objet sélectionné ne sont pas affichés dans le **Interfaces** boîte.  
  
|Bouton de transfert|Description|  
|---------------------|-----------------|  
|**>**|Ajoute à la **implémentent des interfaces** liste le nom d’interface actuellement sélectionné dans le **Interfaces** liste.|  
|**>>**|Ajoute à la **implémentent des interfaces** répertorier tous les noms d’interface disponibles dans le **Interfaces** liste.|  
|**<**|Supprime le nom d’interface actuellement sélectionné dans le **implémentent des interfaces** liste.|  
|**<\<**|Supprime tous les noms de l’interface du **implémentent des interfaces** liste.|  
  
 **Implémenter les Interfaces**  
 Affiche les noms des interfaces que vous avez choisi de mettre en œuvre sur votre objet.  
  
> [!NOTE]
>  Si vous incluez plus d’une interface qui dérive de `IDispatch`, ou si vous essayez d’implémenter une interface qui est dérivée d’une autre interface déjà présente dans votre classe, vous devez lever toute ambiguïté les entrées COM_MAP. Consultez [COM_INTERFACE_ENTRY2](../atl/reference/com-interface-entry-macros.md#com_interface_entry2) pour plus d’informations.  
  
## <a name="see-also"></a>Voir aussi  
 [Implémentation d’une Interface](../ide/implementing-an-interface-visual-cpp.md)