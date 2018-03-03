---
title: "Ajout de prise en charge ATL à votre projet MFC | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.adding.atl.mfc
dev_langs:
- C++
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: b5fe15d6-7752-4818-b9f9-62482ad35c95
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 92a4e9096cf72f6556c8ceb36e12cdff97139712
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-atl-support-to-your-mfc-project"></a>Ajout de la prise en charge ATL à votre projet MFC
Si vous avez déjà créé une application basée sur MFC, puis vous pouvez ajouter la prise en charge pour la bibliothèque ATL (Active Template) facilement en exécutant l’ajouter prise en charge ATL à l’Assistant de projet MFC.  
  
> [!NOTE]
>  ATL et MFC ne sont généralement pas prises en charge dans les éditions Express de Visual Studio.  
  
> [!NOTE]
>  Cette prise en charge s’applique uniquement aux objets simples COM ajoutés à un projet DLL ou un exécutable MFC. Vous pouvez ajouter des autres objets COM (y compris les contrôles ActiveX) à des projets MFC, mais les objets peut ne pas fonctionnent comme prévu.  
  
### <a name="to-add-atl-support-to-your-mfc-project"></a>Pour ajouter la prise en charge ATL à votre projet MFC  
  
1.  Dans l’Explorateur de solutions, cliquez sur le projet auquel vous souhaitez ajouter la prise en charge ATL.  
  
2.  Dans le menu contextuel, cliquez sur **ajouter**, puis cliquez sur **ajouter une classe**.  
  
3.  Sélectionnez le **ajouter la prise en charge ATL aux MFC** icône.  
  
    > [!NOTE]
    >  Cette icône se trouve dans le dossier ATL le **catégories** volet.  
  
4.  Lorsque vous y êtes invité, cliquez sur **Oui** pour ajouter la prise en charge ATL.  
  
 Pour plus d’informations sur la façon dont l’ajout d’une prise en charge ATL modifie le code de votre projet MFC, consultez [détails de la prise en charge ATL ajoutée par l’Assistant ATL](../../mfc/reference/details-of-atl-support-added-by-the-atl-wizard.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Ajout d’une classe](../../ide/adding-a-class-visual-cpp.md)   
 [Ajout de fonctionnalités à l’aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Ajout d’une fonction membre](../../ide/adding-a-member-function-visual-cpp.md)   
 [Ajout d’une Variable membre](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Une fonction virtuelle de substitution](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Gestionnaire de messages MFC](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigation dans la Structure de classe](../../ide/navigating-the-class-structure-visual-cpp.md)
