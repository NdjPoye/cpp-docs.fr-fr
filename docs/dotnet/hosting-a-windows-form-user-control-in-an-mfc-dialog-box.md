---
title: "Hébergement de Windows de former le contrôle utilisateur dans la boîte de dialogue MFC | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: da8e8a54947b329fe36eea5c80bdc13ba5cdfa74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>Hébergement d'un contrôle utilisateur Windows Form dans une boîte de dialogue MFC
MFC héberge un contrôle Windows Forms sous la forme d’un type spécial de contrôle ActiveX et communique avec le contrôle à l’aide des interfaces ActiveX et les propriétés et méthodes de la <xref:System.Windows.Forms.Control> classe. Nous vous recommandons d’utiliser les méthodes et propriétés .NET Framework pour agir sur le contrôle.  
  
 Pour un exemple d’application qui affiche des Windows Forms avec les MFC, consultez [intégration de Windows Forms et MFC](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
> [!NOTE]
>  Dans la version actuelle, un `CDialogBar` objet ne peut pas héberger des contrôles Windows Forms.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Guide pratique pour créer le contrôle utilisateur et l’héberger dans une boîte de dialogue](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)  
  
 [Comment : effectuer une liaison de données DDX/DDV avec Windows Forms](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)  
  
 [Guide pratique pour recevoir des événements Windows Forms de classes C++ natives](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)  
  
## <a name="reference"></a>Référence  
 [Classe de CWinFormsControl](../mfc/reference/cwinformscontrol-class.md) &#124; [CDialog (classe)](../mfc/reference/cdialog-class.md) &#124; [Classe CWnd](../mfc/reference/cwnd-class.md) &#124;<xref:System.Windows.Forms.Control>  
  
## <a name="see-also"></a>Voir aussi  
 [À l’aide d’un contrôle d’utilisateur Windows Form dans MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Différences de programmation entre Windows Forms et MFC](../dotnet/windows-forms-mfc-programming-differences.md)   
 [Hébergement d’un contrôle utilisateur de Windows Forms en tant que vue MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [Hébergement d’un contrôle utilisateur Windows Form en tant que boîte de dialogue MFC](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)