---
title: Ajoutez la classe à partir de l’Assistant contrôle ActiveX | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.class.axcontrol
dev_langs:
- C++
helpviewer_keywords:
- ActiveX Control Wizard
- Add Class from ActiveX Control Wizard [C++]
ms.assetid: 668d801c-5fb6-4176-9191-5c38995a4713
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ab96943e47287c9b54753c8d3a1edb868804274
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="add-class-from-activex-control-wizard"></a>Assistant Ajout d’une classe à partir d’un contrôle ActiveX
Utilisez cet Assistant pour ajouter une classe MFC à partir d’un contrôle ActiveX disponible. L’Assistant crée une classe pour chaque interface que vous ajoutez à partir du contrôle ActiveX sélectionné.  
  
 **Ajouter une classe à partir de**  
 Spécifie l’emplacement de la bibliothèque de types à partir de laquelle la classe est créée.  
  
|Option|Description|  
|------------|-----------------|  
|**Registry**|La bibliothèque de types est enregistrée dans le système. Bibliothèques de types inscrits sont répertoriés dans **contrôles ActiveX disponibles**.|  
|**Fichier**|La bibliothèque de types n’est pas nécessairement inscrite dans le système, mais est contenue dans un fichier. Vous devez fournir l’emplacement du fichier dans **emplacement**.|  
  
 **Contrôles ActiveX disponibles**  
 Spécifie les contrôles ActiveX actuellement inscrits dans le système. Sélectionnez un contrôle ActiveX dans cette liste pour afficher ses interfaces dans les **Interfaces** liste. Consultez [contrôles ActiveX MFC : distribution de contrôles ActiveX](../mfc/mfc-activex-controls-distributing-activex-controls.md) pour plus d’informations sur l’inscription des contrôles ActiveX.  
  
 Si vous cliquez sur **fichier** sous **ajouter une classe à partir**, cette case n’est pas disponible pour modification.  
  
 **Emplacement**  
 Spécifie l’emplacement du contrôle ActiveX. Si vous cliquez sur **fichier** sous **ajouter une classe à partir**, vous pouvez fournir l’emplacement du fichier contenant la bibliothèque de types. Pour accéder à l’emplacement du fichier, cliquez sur le bouton de sélection.  
  
 Si vous cliquez sur **Registre** sous **ajouter une classe à partir**, cette case n’est pas disponible pour modification.  
  
 **Interfaces**  
 Spécifie les interfaces du contrôle ActiveX sélectionné dans **contrôles ActiveX disponibles** ou dans le fichier spécifié dans la bibliothèque de types **emplacement**.  
  
|Bouton de transfert|Description|  
|---------------------|-----------------|  
|**>**|Ajoute l’interface actuellement sélectionné dans le **Interfaces** liste. Non disponible si aucune interface n’est sélectionnée.|  
|**>>**|Ajoute toutes les interfaces dans le contrôle ActiveX sélectionné dans **contrôles ActiveX disponibles** ou dans le fichier spécifié dans la bibliothèque de types **emplacement**.|  
|**<**|Supprime la classe actuellement sélectionnée dans le **classes générées** liste. Non disponible si aucune classe n’est actuellement sélectionné dans le **classes générées** liste.|  
|**<\<**|Supprime toutes les classes dans le **classes générées** liste. If indisponible le **classes générées** liste est vide.|  
  
 **Classes générées**  
 Spécifie les noms de classe à générer à partir des interfaces ajoutées à l’aide de la **>** ou **>>** bouton. Vous pouvez cliquer sur cette zone pour sélectionner une classe, puis haut ou bas pour faire défiler la liste, afficher chaque nom de classe dans le `Class` boîte et nom de fichier dans le **fichier .h** boîte généré par l’Assistant lorsque vous cliquez sur  **Terminer**. Vous pouvez sélectionner qu’une seule classe à la fois dans cette zone.  
  
 Vous pouvez supprimer une classe en la sélectionnant dans cette liste en cliquant sur **<**. Vous n’avez pas besoin de sélectionner une classe dans le **classes générées** boîte pour supprimer toutes les classes ; en cliquant sur **<<**, vous supprimez toutes les classes dans le **classes générées** zone.  
  
 `Class`  
 Spécifie le nom de la classe sélectionnée dans la **classes générées** zone que l’Assistant ajoute lorsque vous cliquez sur **Terminer**. Vous pouvez modifier le nom dans la `Class` boîte.  
  
 **fichier .h**  
 Définit le nom du fichier d’en-tête pour la nouvelle classe d’objet. Par défaut, ce nom est basé sur le nom que vous fournissez dans **classes générées**. Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l’emplacement de votre choix ou pour ajouter la déclaration de classe à un fichier existant. Si vous choisissez un fichier existant, l’Assistant enregistrera pas à l’emplacement sélectionné jusqu'à ce que vous cliquez sur **Terminer** dans l’Assistant.  
  
 L’Assistant ne remplacera pas un fichier. Si vous sélectionnez le nom d’un fichier existant, lorsque vous cliquez sur **Terminer**, l’Assistant vous invite à indiquer si la déclaration de classe doit être ajoutée au contenu du fichier. Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **non** pour revenir à l’Assistant et spécifiez un autre nom de fichier.  
  
 **fichier .cpp**  
 Définit le nom du fichier d’implémentation pour la nouvelle classe d’objet. Par défaut, ce nom est basé sur le nom que vous fournissez dans **classes générées**. Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l’emplacement de votre choix. Le fichier n’est pas enregistré à l’emplacement sélectionné jusqu'à ce que vous cliquez sur **Terminer** dans l’Assistant.  
  
 L’Assistant ne remplacera pas un fichier. Si vous sélectionnez le nom d’un fichier existant, lorsque vous cliquez sur **Terminer**, l’Assistant vous invite à indiquer si l’implémentation de classe doit être ajoutée au contenu du fichier. Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **non** pour revenir à l’Assistant et spécifiez un autre nom de fichier.  
  
## <a name="see-also"></a>Voir aussi  
 [Ajout d’une classe à partir d’un contrôle ActiveX](../ide/adding-a-class-from-an-activex-control-visual-cpp.md)   
 [Clients Automation : utilisation des bibliothèques de types](../mfc/automation-clients-using-type-libraries.md)