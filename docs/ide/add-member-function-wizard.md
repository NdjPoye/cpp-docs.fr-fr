---
title: "Assistant Ajout de fonction membre | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.function.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ajout de fonction membre (Assistant C++)"
ms.assetid: 13b6defc-faa6-4d57-83db-9dd854cbea3d
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Assistant Ajout de fonction membre
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet Assistant ajoute une déclaration de fonction membre au fichier d'en\-tête et une implémentation de fonction membre stub au fichier d'implémentation pour la classe sélectionnée.  
  
 Lorsque vous avez ajouté la fonction membre à l'aide de l'Assistant, vous pouvez modifier le code dans l'environnement de développement.  
  
 **Type de retour**  
 Définit le type de retour pour la fonction membre que vous ajoutez.  Vous pouvez fournir votre propre type de retour ou le sélectionner dans la liste des types disponibles.  Pour plus d'informations sur les types, consultez [Types fondamentaux](../cpp/fundamental-types-cpp.md).  
  
||||  
|-|-|-|  
|`char`|`int`|`unsigned int`|  
|**double**|**long**|`unsigned long`|  
|**float**|**short**|`void`|  
|`HRESULT`|`unsigned char`||  
  
 **Nom de la fonction**  
 Définit le nom de la fonction membre que vous ajoutez.  
  
 **Type de paramètre**  
 Définit le type de paramètre que vous ajoutez à la fonction membre, si elle possède des paramètres.  Vous pouvez fournir votre propre type de paramètre ou le sélectionner dans la liste des types disponibles.  
  
||||  
|-|-|-|  
|`char`|`int`|`unsigned char`|  
|**double**|**long**|`unsigned int`|  
|**float**|**short**|`unsigned long`|  
  
 **Nom du paramètre**  
 Définit le nom d'un paramètre que vous ajoutez à la fonction membre, si elle possède des paramètres.  
  
 **Liste de paramètres**  
 Affiche la liste des paramètres que vous avez ajoutés à la fonction membre.  Pour ajouter un paramètre à la liste, spécifiez un type et un nom dans les zones **Type de paramètre** et **Nom du paramètre**, puis cliquez sur **Ajouter**.  Pour supprimer un paramètre de la liste, sélectionnez\-le et cliquez sur **Supprimer**.  
  
 **Accès**  
 Définit l'accès à la fonction membre.  Les modificateurs d'accès sont des mots clés spécifiant le type d'accès dont disposent les autres classes en ce qui concerne la fonction membre.  Pour plus d'informations sur la spécification de l'accès, consultez [Contrôle d'accès des membres](../cpp/member-access-control-cpp.md).  Par défaut, le niveau d'accès à la fonction membre a la valeur **public**.  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
 Vérifiez si la nouvelle fonction membre est statique ou virtuelle, ainsi que si elle est inline ou pure.  Si vous définissez la fonction membre comme pure, la case à cocher `Virtual` est activée et la case à cocher **Inline** n'est pas disponible.  Par défaut la fonction membre est non statique et non virtuelle.  
  
|Option|Description|  
|------------|-----------------|  
|[Static](../misc/static-cpp.md)|Spécifie que la fonction agit comme une fonction globale et peut être appelée à l'extérieur de la classe, même sans instanciation de classe.  La fonction membre n'a pas accès aux membres non statiques.  Une fonction membre spécifiée comme `Static` ne peut pas être virtual.|  
|[Virtuel](../cpp/virtual-cpp.md)|Vérifiez si la fonction membre correcte est appelée pour un objet, quelle que soit l'expression utilisée pour lancer l'appel de fonction membre.  Une fonction membre spécifiée comme `Virtual` ne peut pas être static.|  
|**Pure**|Indique qu'aucune implémentation n'est proposée pour la fonction membre virtuelle déclarée. Par conséquent, l'option **Pure** ne peut être spécifiée que sur des fonctions membres virtuelles.  Pour plus d'informations, consultez [Syntaxe de déclaration de membre de classe](../misc/class-member-declaration-syntax.md).<br /><br /> Une classe contenant au moins une fonction membre virtuelle pure est considérée comme une classe abstraite.  Les classes dérivées de la classe abstraite doivent implémenter la fonction membre virtuelle pure. Sinon, elles sont également des classes abstraites.|  
|[Inline](../cpp/inline-functions-cpp.md)|Ordonne au compilateur d'insérer une copie du corps de la fonction membre à chaque endroit auquel la fonction membre est appelée.  Une fonction membre spécifiée comme **Inline** ne peut pas être pure.|  
  
 **fichier .cpp**  
 Définit l'emplacement du fichier dans lequel l'implémentation de la fonction membre stub est écrite.  Par défaut, il s'agit du fichier .cpp de la classe à laquelle la fonction membre est ajoutée.  Cliquez sur le bouton de sélection pour modifier le nom du fichier.  L'implémentation de la fonction membre est ajoutée au contenu du fichier sélectionné.  
  
 **Commentaire**  
 Ajoute un commentaire dans le fichier d'en\-tête de la fonction membre.  
  
 **Signature de la fonction**  
 Affiche la fonction membre telle qu'elle apparaît dans le code lorsque vous cliquez sur **Terminer**.  Vous ne pouvez pas modifier le texte dans cette zone.  Pour modifier la fonction membre, changez les zones appropriées de l'Assistant.  
  
## Voir aussi  
 [Ajout d'une fonction membre](../ide/adding-a-member-function-visual-cpp.md)