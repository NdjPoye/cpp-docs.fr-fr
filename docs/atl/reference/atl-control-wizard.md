---
title: "Assistant contrôle ATL | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding controls
- controls [ATL], adding to projects
- ATL Control Wizard
ms.assetid: 991f8e72-ffbc-4382-a4ce-e255acfba5b6
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 586ac14878ccd6908d025d706b72f3c9856d1b39
ms.lasthandoff: 02/24/2017

---
# <a name="atl-control-wizard"></a>Assistant Contrôle ATL
Insère dans un projet ATL (ou un projet MFC avec prise en charge ATL) un contrôle ATL. Vous pouvez utiliser cet Assistant pour insérer l’un des trois types de contrôles :  
  
-   Contrôle standard  
  
-   Contrôle composite  
  
-   Contrôle DHTML  
  
 En outre, vous pouvez spécifier un contrôle minimal, supprimant les interfaces à partir de la [Interfaces](../../atl/reference/interfaces-atl-control-wizard.md) liste, qui sont fournis comme paramètres par défaut pour les contrôles pour l’ouvrir dans la plupart des conteneurs. Vous pouvez définir les interfaces que vous souhaitez pris en charge pour le contrôle de la **Interfaces** page de l’Assistant.  
  
## <a name="remarks"></a>Notes  
 Le script d’inscription produit par cet Assistant inscrira ses composants COM sous HKEY_CURRENT_USER au lieu de HKEY_LOCAL_MACHINE. Pour modifier ce comportement, définissez la **inscrire le composant pour tous les utilisateurs** option de l’Assistant ATL.  
  
## <a name="names"></a>Noms  
 Spécifiez les noms de l’objet, interface et les classes à ajouter à votre projet. À l’exception de **nom court**, toutes les autres zones peuvent être modifiées indépendamment. Si vous modifiez le texte **nom court**, la modification est répercutée dans les noms de toutes les autres zones de cette page. Si vous modifiez le **coclasse** nom de la section COM, la modification est répercutée dans le **Type** zone, mais le **Interface** nom et **ProgID** ne changent pas. Ce comportement d’affectation de noms est conçu pour rendre tous les noms facilement identifiables pour vous lorsque vous développez votre contrôle.  
  
> [!NOTE]
>  **Coclasse** est modifiable uniquement les contrôles sans attributs. Si votre projet comporte des attributs, vous ne pouvez pas modifier **coclasse**.  
  
### <a name="c"></a>C++  
 Fournit des informations pour la classe C++ créée pour implémenter l’objet.  
  
 **Nom court**  
 Définit le nom abrégé de l’objet. Le nom que vous entrez détermine la classe et **coclasse** noms, le fichier (. CPP et. H) noms, le nom de l’interface et le **Type** noms, sauf si vous modifiez ces champs individuellement.  
  
 **(Classe)**  
 Définit le nom de la classe qui implémente l’objet. Ce nom est basé sur le nom que vous fournissez dans **nom court**, précédé de « C » (préfixe classique pour un nom de classe.  
  
 **fichier .h**  
 Définit le nom du fichier d’en-tête pour la nouvelle classe d’objet. Par défaut, ce nom est basé sur le nom que vous fournissez dans **nom court**. Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l’emplacement de votre choix ou pour ajouter la déclaration de classe à un fichier existant. Si vous sélectionnez un fichier existant, l’Assistant ne sera pas enregistrer dans l’emplacement sélectionné jusqu'à ce que vous cliquez sur **Terminer**.  
  
 L’Assistant n’écrase pas un fichier. Si vous sélectionnez le nom d’un fichier existant, cliquez sur **Terminer**, l’Assistant vous invite à indiquer si la déclaration de classe doit être ajoutée au contenu du fichier. Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **non** pour revenir à l’Assistant et spécifiez un autre nom de fichier.  
  
 **fichier .cpp**  
 Définit le nom du fichier d’implémentation pour la nouvelle classe d’objet. Par défaut, ce nom est basé sur le nom que vous fournissez dans **nom court**. Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l’emplacement de votre choix. Le fichier n’est pas enregistré à l’emplacement sélectionné jusqu'à ce que vous cliquiez **Terminer** dans l’Assistant.  
  
 L’Assistant n’écrase pas un fichier. Si vous sélectionnez le nom d’un fichier existant, cliquez sur **Terminer**, l’Assistant vous invite à indiquer si l’implémentation de classe doit être ajoutée au contenu du fichier. Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **non** pour revenir à l’Assistant et spécifiez un autre nom de fichier.  
  
 **Par attributs**  
 Indique si l’objet utilise des attributs. Si vous ajoutez un objet à un projet ATL avec attributs, cette option est sélectionnée et non disponible pour modification. Autrement dit, vous pouvez ajouter uniquement les objets attribués à un projet créé avec prise en charge de l’attribut.  
  
 Vous pouvez ajouter un objet attribué qu’à un projet ATL qui utilise des attributs. Si vous sélectionnez cette option pour un projet ATL ne prenant pas en charge les attributs, l’Assistant vous invite à spécifier si vous souhaitez ajouter la prise en charge de l’attribut pour le projet.  
  
 Par défaut, les objets que vous ajoutez après avoir défini cette option sont désignés avec attributs (la case à cocher est sélectionnée). Vous pouvez désactiver cette case pour ajouter un objet qui n’utilise pas d’attributs.  
  
 Consultez la page [paramètres de l’Application, Assistant Projet ATL](../../atl/reference/application-settings-atl-project-wizard.md) et [mécanismes de base des attributs](../../windows/basic-mechanics-of-attributes.md) pour plus d’informations.  
  
### <a name="com"></a>COM  
 Fournit des informations sur les fonctionnalités COM pour l’objet.  
  
 **Coclasse**  
 Définit le nom de la classe de composant qui contient la liste des interfaces prises en charge par l’objet.  
  
> [!NOTE]
>  Si vous créez votre projet à l’aide d’attributs, ou si vous indiquez sur cette page de l’Assistant que le contrôle utilise des attributs, vous ne pouvez pas modifier cette option, car ATL n’inclut pas le **coclasse** attribut.  
  
 **Interface**  
 Définit le nom de l’interface de l’objet. Par défaut un nom d’interface est précédé de « I ».  
  
 **Type**  
 Définit la description de l’objet qui apparaîtra dans le Registre  
  
 **ProgID**  
 Définit le nom que les conteneurs peuvent utiliser plutôt que le CLSID de l’objet. Ce champ n’est pas renseigné automatiquement. Si vous ne remplissez pas ce champ manuellement, le contrôle n’est peut-être pas disponible à d’autres outils. Par exemple, les contrôles ActiveX générés sans un `ProgID` ne sont pas disponibles dans les **insérer un contrôle ActiveX** boîte de dialogue. Pour plus d’informations sur la boîte de dialogue, consultez [boîte de dialogue Insérer le contrôle ActiveX](../../windows/insert-activex-control-dialog-box.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle ATL](../../atl/reference/adding-an-atl-control.md)   
 [Ajout d’une fonctionnalité au contrôle Composite](../../atl/adding-functionality-to-the-composite-control.md)   
 [Principes de base des objets ATL COM](../../atl/fundamentals-of-atl-com-objects.md)


