---
title: "TN023&#160;: ressources MFC standard | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.resources"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ressources (MFC)"
  - "ressources standard"
  - "TN023"
ms.assetid: 60af8415-c576-4c2f-a711-ca5da0b9a1f2
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# TN023&#160;: ressources MFC standard
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette remarque décrit les ressources standard prédites et requises par la bibliothèque MFC.  
  
## Ressources standard  
 MFC propose deux catégories de ressources prédéfinis que vous pouvez utiliser dans votre application : ressources image clipart et ressources standard en infrastructure.  
  
 Les ressources image clipart sont des ressources supplémentaires que l'infrastructure ne dépend pas de fonction, mais que vous pouvez souhaiter ajouter à l'interface utilisateur de l'application.  Les ressources suivantes en image clipart figurent dans l'exemple de [CLIPART](../top/visual-cpp-samples.md)de MFC :  
  
-   Common.rc : Un seul fichier de ressources qui contient :  
  
    -   Une grande collection d'icônes qui représentent une série d'entreprise et des travaux mécanographiques.  
  
    -   Plusieurs curseurs communs \(voir aussi l'Afxres.rc\).  
  
    -   Bitmap de la barre d'outils qui contient plusieurs boutons de la barre d'outils.  
  
    -   Les ressources Bitmap et icône utilisées par Commdlg.dll.  
  
-   Indicate.rc : Contient des ressources de chaîne pour les indicateurs d'état du bouton de la barre d'état, tels que « CAP » pour la fonction upper\-case.  
  
-   Prompts.rc : Contient des ressources de chaîne en menu\- ligne pour chaque commande prédéfinie, par exemple « créer un document » pour `ID_FILE_NEW`.  
  
-   Commdlg.rc : Un fichier compatible Visual C\+\+ .rc qui contient les modèles de la boîte de dialogue standard COMMDLG.  
  
 Les ressources en infrastructure standard sont des ressources avec des ID AFX\- définis sur lesquelles l'infrastructure dépend pour des implémentations internes.  Vous devez fréquemment modifier ces ressources AFX\- définies.  Dans ce cas, vous devez suivre la procédure soulignée les grandes lignes plus loin dans cette rubrique.  
  
 Les ressources suivantes en infrastructure sont contenues dans le répertoire MFC\\Include :  
  
-   Afxres.rc : Ressources courantes par l'infrastructure.  
  
-   Afxprint.rc : Ressources spécifiques à imprimer.  
  
-   Afxolecl.rc : Ressources spécifiques à OLE applications clientes.  
  
-   Afxolev.rc : Ressources spécifiques aux applications serveur OLE complètes.  
  
## Utilisation des ressources image clipart  
  
#### Pour utiliser une ressource binaire d'image clipart  
  
1.  Ouvrez le fichier des ressources de votre application dans Visual C\+\+.  
  
2.  Ouvrez Common.rc.  Ce fichier contient toutes les ressources binaires en image clipart.  Cette opération peut prendre quelque temps car le fichier de Common.rc est compilé.  
  
3.  Maintenez la touche CTRL enfoncée pendant que vous faites glisser les ressources à utiliser dans Common.rc au fichier des ressources de votre application.  
  
 Pour utiliser d'autres ressources image clipart, suivez les mêmes étapes.  La seule différence est que vous ouvrirez le fichier approprié de .rc au lieu de Common.rc.  
  
> [!NOTE]
>  Faites attention de ne pas déplacer involontairement des ressources en dehors de Common.rc définitivement.  Si vous maintenez la touche CTRL enfoncée pendant que vous faites glisser des ressources, vous allez créer une copie.  Si vous ne conservez pas la touche CTRL enfoncée pendant que vous faites glisser, les ressources seront déplacées.  Si vous êtes concerné que vous avez pu accidentellement apporté des modifications au fichier de Common.rc, cliquez sur « no » lorsque vous êtes invité à enregistrer ou non les modifications apportées à Common.rc.  
  
> [!NOTE]
>  Les fichiers de ressources de .rc ont une ressource particulière en `TEXTINCLUDE` qu'elles que vous empêchent de journalisation par erreur sur les fichiers standard .rc.  
  
### Personnaliser les ressources en infrastructure standard  
 Les ressources en infrastructure standard sont généralement incluses dans une application avec la commande de \#include dans le fichier de ressources d'une application.  AppWizard génère un fichier de ressources.  Ce fichier contient des ressources infrastructure de niveau adéquat, selon lesquelles les options d'AppWizard vous sélectionnez.  Vous pouvez examiner, ajouter ou supprimer les ressources sont incluses en modifiant les directives de compilation.  Pour cela, ouvrez le menu **Ressource** et sélectionnez **Définir les inclusions**.  Recherchez l'élément de modification « directives de compilation ».  Par exemple :  
  
```  
#include "afxres.rc"  
#include "afxprint.rc"  
```  
  
 La plupart des cas courants de personnalisation les ressources standard en infrastructure est d'ajouter ou supprimer les inclusions supplémentaires pour l'impression, OLE client, et OLE prise en charge de serveur.  
  
 Dans certains cas exceptionnels vous pouvez personnaliser le contenu des ressources standard en infrastructure pour votre application spécifique, pas seulement pour ajouter et supprimer le fichier complet.  Les étapes suivantes montrent comment vous pouvez limiter les ressources qui sont incluses :  
  
##### Pour personnaliser le contenu d'un fichier de ressources standard  
  
1.  Ouvrez le fichier de ressources dans Visual C\+\+.  
  
2.  Lors de l'utilisation de l'ensemble des ressources inclut la commande, supprimez `#include` du fichier standard .rc que vous souhaitez personnaliser.  Par exemple, pour personnaliser la barre d'outils d'aperçu avant impression, supprimez la ligne `#include "afxprint.rc"`.  
  
3.  Ouvrez les fichiers de ressources de niveau adéquat de MFC\\LES INCLUDE.  Après l'exemple précédent de cette rubrique, le fichier approprié est MFC incluent\\\\ Aafxprint.rc  
  
4.  Copiez toutes les ressources du fichier standard .rc à votre fichier de ressources d'application.  
  
5.  Modifiez la copie des ressources standard dans votre fichier de ressources d'application.  
  
> [!NOTE]
>  Ne modifiez pas les ressources directement dans les fichiers standard .rc.  Ce qui modifie les ressources disponibles dans chaque application, et non dans celle que vous utilisez actuellement sur.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)