---
title: Assistant Ajout d’événement | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.event.overview
dev_langs:
- C++
helpviewer_keywords:
- Add Event Wizard [C++]
ms.assetid: bdd2a7bb-13d5-44d7-abc9-e785ba4e05ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f92f871f22fb01f3f0f37677c393fcd481c08120
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="add-event-wizard"></a>Assistant Ajout d'événement
Cet Assistant ajoute un événement à un projet de contrôle ActiveX MFC. Vous pouvez spécifier votre propre événement, vous pouvez personnaliser un événement stock en général, ou vous pouvez sélectionner dans la liste des événements stock.  
  
 **Nom de l’événement**  
 Définit le nom utilisé par les clients Automation pour demander un événement à partir de la classe. Entrez un nom ou sélectionnez-en un dans la liste.  
  
 **Type d’événement**  
 Indique le type d’événement à ajouter. Disponible uniquement si vous sélectionnez à partir de la **nom de l’événement** liste.  
  
|Option|Description|  
|------------|-----------------|  
|**Stock**|Spécifie qu’un événement stock, tel qu’un clic de bouton, sera implémenté pour cette classe. Événements stock sont définis dans la bibliothèque Microsoft Foundation classes (MFC).|  
|**Personnalisé**|Spécifie que vous fournissez votre propre implémentation de l’événement.|  
  
 **Nom interne**  
 Définit le nom de la fonction membre qui envoie l’événement. Disponible uniquement pour les événements personnalisés. Le nom est basé sur **nom de l’événement**. Vous pouvez modifier le nom interne si vous souhaitez fournir un nom différent de celui **nom de l’événement**.  
  
 **Type de paramètre**  
 Définit le type pour le **nom de paramètre**. Sélectionnez le type dans la liste.  
  
 **Nom du paramètre**  
 Définit le nom d’un paramètre à passer à l’événement. Après avoir tapé le nom, vous devez cliquer sur **ajouter** à ajouter à la liste de paramètres.  
  
 Une fois que vous cliquez sur **ajouter**, le nom du paramètre s’affiche dans **liste de paramètres**.  
  
> [!NOTE]
>  Si vous fournissez un nom de paramètre, puis sur **Terminer** avant de cliquer sur **ajouter**, le paramètre n’est pas ajoutée à l’événement. Vous devez rechercher la méthode et insérer le paramètre manuellement. **Liste de paramètres**  
  
 **Ajouter**  
 Ajoute le paramètre que vous spécifiez dans **nom de paramètre**et son type, à **liste de paramètres**. Vous devez cliquer sur **ajouter** pour ajouter un paramètre à la liste.  
  
 **Supprimer**  
 Supprime le paramètre que vous sélectionnez dans **liste de paramètres** dans la liste.  
  
 **Liste de paramètres**  
 Affiche tous les paramètres et leurs types actuellement ajoutés pour la méthode. Lorsque vous ajoutez des paramètres, l’Assistant met à jour **liste de paramètres** pour afficher chaque paramètre avec son type.  
  
## <a name="see-also"></a>Voir aussi  
 [Ajout d’un événement](../ide/adding-an-event-visual-cpp.md)