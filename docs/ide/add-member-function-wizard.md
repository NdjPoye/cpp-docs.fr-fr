---
title: Assistant Ajout de membre fonction | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.function.overview
dev_langs:
- C++
helpviewer_keywords:
- Add Member Function Wizard [C++]
ms.assetid: 13b6defc-faa6-4d57-83db-9dd854cbea3d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 775b519b304549b474cd21980ef5a4cbe8f2d4d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="add-member-function-wizard"></a>Assistant Ajout de fonction membre
Cet Assistant ajoute une déclaration de fonction membre pour le fichier d’en-tête et une implémentation de fonction membre stub pour le fichier d’implémentation pour la classe sélectionnée.  
  
 Une fois que vous avez ajouté la fonction membre à l’aide de l’Assistant, vous pouvez modifier le code dans l’environnement de développement.  
  
 **Type de retour**  
 Définit le type de retour pour la fonction membre que vous ajoutez. Vous pouvez fournir votre propre type de retour, ou vous pouvez sélectionner dans la liste des types disponibles. Pour plus d’informations sur les types, consultez [Types fondamentaux](../cpp/fundamental-types-cpp.md).  
  
||||  
|-|-|-|  
|`char`|`int`|`unsigned int`|  
|**double**|**long**|`unsigned long`|  
|**float**|**short**|`void`|  
|`HRESULT`|`unsigned char`||  
  
 **Nom de la fonction**  
 Définit le nom de la fonction membre que vous ajoutez.  
  
 **Type de paramètre**  
 Définit le type de paramètre que vous ajoutez pour la fonction membre, si la fonction membre possède des paramètres. Vous pouvez fournir votre propre type de paramètre, ou vous pouvez sélectionner dans la liste des types disponibles.  
  
||||  
|-|-|-|  
|`char`|`int`|`unsigned char`|  
|**double**|**long**|`unsigned int`|  
|**float**|**short**|`unsigned long`|  
  
 **Nom du paramètre**  
 Définit le nom d’un paramètre que vous ajoutez pour la fonction membre, si la fonction membre possède des paramètres.  
  
 **Liste de paramètres**  
 Affiche une liste de paramètres que vous avez ajouté à la fonction membre. Pour ajouter un paramètre à la liste, fournissez un type et nom dans la **type de paramètre** et **nom de paramètre** et cliquez sur **ajouter**. Pour supprimer un paramètre dans la liste, sélectionnez le paramètre et cliquez sur **supprimer**.  
  
 **Accès**  
 Définit l’accès à la fonction membre. Modificateurs d’accès sont des mots clés qui spécifient l’accès des autres classes à la fonction membre. Consultez [le contrôle d’accès de membre](../cpp/member-access-control-cpp.md) pour plus d’informations sur la spécification de l’accès. Le niveau d’accès de fonction membre a la valeur **public** par défaut.  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
 Vérifiez que la nouvelle fonction membre est statique ou virtuelle, et si elle est inline ou pure. Si vous définissez la fonction membre comme pure, la `Virtual` case à cocher est activée et le **Inline** case à cocher n’est plus disponible. La valeur par défaut est une fonction membre non statique et non virtuelle.  
  
|Option|Description|  
|------------|-----------------|  
|[Static](../cpp/storage-classes-cpp.md)|Spécifie que la fonction agit comme un global et peut être appelée en dehors de la classe, même sans instanciation de classe. La fonction membre n’a aucun accès aux membres non statiques. Une fonction membre spécifiée comme `Static` ne peut pas être virtuel.|  
|[Virtuel](../cpp/virtual-cpp.md)|Garantit que la fonction membre correcte est appelée pour un objet, quelle que soit l’expression utilisée pour appeler la fonction membre. Une fonction membre spécifiée comme `Virtual` ne peut pas être statique.|  
|**Pure**|Indique qu’aucune implémentation n’est fournie pour la fonction membre virtuelle déclarée. Par conséquent, **Pure** peut être spécifié uniquement sur les fonctions membres virtuelles. Une classe qui contient au moins une fonction membre virtuelle pure est considérée comme une classe abstraite. Classes dérivées de la classe abstraite doivent implémenter la fonction membre virtuelle pure ou elles aussi sont des classes abstraites.|  
|[Inline](../cpp/inline-functions-cpp.md)|Indique au compilateur d’insérer une copie du corps de la fonction membre dans chaque emplacement où que la fonction membre est appelée. Une fonction membre spécifiée comme **Inline** ne peut pas être pure.|  
  
 **fichier .cpp**  
 Définit l’emplacement du fichier où l’implémentation de fonction membre stub est écrite. Par défaut, il est écrit dans le fichier .cpp de la classe à laquelle la fonction membre est ajoutée. Cliquez sur le bouton de sélection pour modifier le nom de fichier. L’implémentation de la fonction membre est ajoutée au contenu du fichier sélectionné.  
  
 **Commentaire**  
 Fournit un commentaire dans le fichier d’en-tête pour la fonction membre.  
  
 **Signature de fonction**  
 Affiche la fonction membre, tel qu’il apparaît dans le code lorsque vous cliquez sur **Terminer**. Vous ne pouvez pas modifier le texte dans cette zone. Pour modifier la fonction membre, modifiez les zones appropriées dans l’Assistant.  
  
## <a name="see-also"></a>Voir aussi  
 [Ajout d’une fonction membre](../ide/adding-a-member-function-visual-cpp.md)