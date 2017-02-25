---
title: "Ajout d&#39;un contr&#244;le (Didacticiel ATL, Partie&#160;2) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: c9575a75-1064-41f1-9697-7aada560c669
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Ajout d&#39;un contr&#244;le (Didacticiel ATL, Partie&#160;2)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans cette étape, vous ajouterez un contrôle à votre projet, le générerez et le testerez sur une page Web.  
  
## Procédures  
  
#### Pour ajouter un objet à un projet ATL  
  
1.  Dans l'Affichage de classes, cliquez avec le bouton droit sur le projet Polygon.  
  
2.  Pointez sur **Ajouter** dans le menu contextuel, puis cliquez sur **Classe** dans le sous\-menu.  
  
     La boîte de dialogue **Ajouter une classe** s'affiche.  Les différentes catégories d'objet sont répertoriées dans l'arborescence à gauche.  
  
3.  Choisissez le dossier **ATL**.  
  
4.  Dans la liste des modèles à droite, sélectionnez **Contrôle ATL**.  Cliquez sur **Ajouter**.  L'Assistant Contrôle ATL s'ouvre, et vous pouvez configurer le contrôle.  
  
5.  Tapez `PolyCtl` comme nom court et notez que les autres champs sont automatiquement remplis.  Ne cliquez pas encore sur **Terminer** car vous devez apporter des modifications.  
  
 La page **Noms** de l'Assistant Contrôle ATL contient les champs suivants :  
  
|Champ|Sommaire|  
|-----------|--------------|  
|**Nom court**|Le nom spécifié pour le contrôle.|  
|**Classe**|Nom de la classe C\+\+ créé pour implémenter le contrôle.|  
|**fichier .h**|Fichier créé pour contenir la définition de la classe C\+\+.|  
|**fichier .cpp**|Fichier créé pour contenir l'implémentation de la classe C\+\+.|  
|**CoClasse**|Le nom de la classe de composant pour ce contrôle.|  
|**Interface**|Le nom de l'interface sur laquelle le contrôle implémente ses méthodes et ses propriétés personnalisées.|  
|**Type**|Description du contrôle.|  
|**ProgID**|Le nom lisible qui peut être utilisé pour rechercher le CLSID du contrôle.|  
  
 Vous devez effectuer plusieurs paramètres supplémentaires dans l'Assistant Contrôle ATL.  
  
#### Pour activer la prise en charge des informations sur l'erreur et les points de connexion riches  
  
1.  Cliquez sur **Options** pour ouvrir la page **Options**.  
  
2.  Activez la case à cocher **Points de connexion**.  Cela créera la prise en charge d'une interface sortante dans le fichier IDL.  
  
 Vous pouvez également rendre le contrôle insérable, ce qui signifie qu'il peut être intégré aux applications prenant en charge les objets incorporés, tels qu'Excel ou Word.  
  
#### Pour rendre le contrôle insérable  
  
1.  Cliquez sur **Apparence** pour ouvrir la page **Apparence**.  
  
2.  Activez la case à cocher **Insérable**.  
  
 Le polygone affiché par l'objet aura une couleur de remplissage unie, vous devez alors ajouter une propriété stock `Fill Color`.  
  
#### Pour ajouter une propriété stock de couleur de remplissage et créer un contrôle  
  
1.  Cliquez sur **Propriétés stock** pour ouvrir la page **Propriétés stock**.  
  
2.  Sous **Non pris en charge**, faites défiler la liste de propriétés stock possibles.  Double\-cliquez sur `Fill Color` pour le placer dans la liste **Pris en charge**.  
  
3.  Cela termine les options pour le contrôle.  Cliquez sur **Terminer**.  
  
 Lorsque l'Assistant a créé le contrôle, plusieurs modifications de code et ajouts de fichiers se sont produits.  Les fichiers suivants ont été créés :  
  
|Fichier|Description|  
|-------------|-----------------|  
|PolyCtl.h|Contient la majeure partie de l'implémentation du `CPolyCtl` de la classe C\+\+.|  
|PolyCtl.cpp|Contient les parties restantes de `CPolyCtl`.|  
|PolyCtl.rgs|Fichier de texte qui contient le script de registre utilisé pour enregistrer le contrôle.|  
|PolyCtl.htm|Page Web contenant une référence au contrôle nouvellement créé.|  
  
 L'Assistant a également exécuté les modifications du code suivantes :  
  
-   Ajout d'une instruction `#include` aux fichiers stdafx.h et stdafx.cpp pour inclure les fichiers ATL nécessaires à la prise en charge des contrôles.  
  
-   Polygon.idl modifié pour inclure les détails du nouveau contrôle.  
  
-   Ajout d'un nouveau contrôle au mappage d'objets dans Polygon.cpp.  
  
 Vous pouvez maintenant générer le contrôle pour le voir en action.  
  
## Génération et test du contrôle  
  
#### Pour générer et tester le contrôle  
  
1.  Dans le menu **Générer**, cliquez sur **Générer le polygone**.  
  
     Une fois que le contrôle a terminé la génération, cliquez avec le bouton droit sur PolyCtl.htm dans l'**Explorateur de solutions** et sélectionnez **Afficher dans le navigateur**.  La page Web HTML contenant le contrôle sera affichée.  Vous devez voir la page portant le titre « Page de test ATL 8.0 pour l'objet PolyCtl » et le texte **PolyCtl**.  Il s'agit de votre contrôle.  
  
> [!NOTE]
>  En effectuant ce didacticiel, si vous recevez un message d'erreur où le fichier DLL ne peut pas être créé, fermez le fichier PolyCtl.htm et l'ActiveX Control Test Container, puis générez à nouveau la solution.  Si vous ne parvenez toujours pas à créer la DLL, redémarrez l'ordinateur ou fermez la session \(si vous utilisez les services Terminal Server\).  
  
 Vous ajouterez ensuite une propriété personnalisée au contrôle.  
  
 [Revenir à l'étape 1](../atl/creating-the-project-atl-tutorial-part-1.md) &#124; [Dans l'étape 3](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md)  
  
## Voir aussi  
 [Didacticiel](../atl/active-template-library-atl-tutorial.md)