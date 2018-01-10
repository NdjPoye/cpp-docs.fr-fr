---
title: -Qfast_transcendentals (Force des fonctions transcendantes rapides) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /Qfast_transcendentals
dev_langs: C++
helpviewer_keywords:
- /Qfast_transcendentals
- Force Fast Transcendentals
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f8d7e8de17c096d061653b469207352be4b9b8bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="qfasttranscendentals-force-fast-transcendentals"></a>/Qfast_transcendentals (Force Fast Transcendentals)
Génère le code inline pour les fonctions transcendantes.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/Qfast_transcendentals  
```  
  
## <a name="remarks"></a>Notes  
 Cette option du compilateur force des fonctions transcendantes à convertir en code inline pour améliorer la vitesse d’exécution. Cette option a un effet uniquement en association avec **/fp : sauf** ou **/fp : precise**. Génération du code incorporé pour les fonctions transcendantes est déjà le comportement par défaut sous **Fast**.  
  
 Cette option n’est pas compatible avec **/fp : strict**. Consultez [/fp (spécifier du comportement de nombres à virgule flottante)](../../build/reference/fp-specify-floating-point-behavior.md) pour plus d’informations sur flottante options du compilateur de point.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **C/C++** .  
  
3.  Cliquez sur la page de propriétés **Ligne de commande** .  
  
4.  Tapez l'option de compilateur dans la zone **Options supplémentaires** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [/Q (opérations de bas niveau), options](../../build/reference/q-options-low-level-operations.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)