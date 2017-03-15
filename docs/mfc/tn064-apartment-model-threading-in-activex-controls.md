---
title: "TN064&#160;: mod&#232;le de thread apartment dans les contr&#244;les ActiveX | Microsoft Docs"
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
  - "vc.controls.activex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "modèle de thread apartment"
  - "conteneurs (C++), multithread"
  - "conteneur multithread"
  - "contrôles OLE, prise en charge des conteneurs"
  - "TN064"
ms.assetid: b2ab4c88-6954-48e2-9a74-01d4a60df073
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN064&#160;: mod&#232;le de thread apartment dans les contr&#244;les ActiveX
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 Cette note technique explique comment activer le threading de modèle d'appartement dans un contrôle ActiveX.  Notez que le threading de modèle d'appartement est pris en charge dans les versions 4.2 Visual C\+\+ ou ultérieures.  
  
## Qu'est\-ce que le threading de modèle d'apartement?  
 Le modèle d'apartement est une approche de prise en charge d'objets incorporés, tels que les contrôles ActiveX, dans une application conteneur multithread.  Bien que l'application puisse avoir plusieurs threads, chaque instance d'un objet incorporé est affectée à un « appartement », qui s'exécute sur un seul thread.  En d'autres termes, tous les appels à une instance d'un contrôle se produisent sur le même thread.  
  
 Toutefois, différentes instances du même type de contrôle peuvent être affectées à des appartements.  Par conséquent, si plusieurs instances d'un contrôle partagent des données en commun \(par exemple, les données statiques ou globales\), alors l'accès à ces données partagées doit être protégé par un objet de synchronisation, tel qu'une section critique.  
  
 Pour les détails complets sur le modèle de thread cloisonné, consultez [Processus et threads](http://msdn.microsoft.com/library/windows/desktop/ms684841) dans *la référence du programmeur OLE*.  
  
## Pourquoi prendre en charge le threading de modèle d'appartement ?  
 Les contrôles qui prennent en charge le threading de modèle d'appartement peuvent être utilisés dans des applications conteneur multithread qui prennent également en charge le modèle d'appartement.  Si vous n'activez pas le threading de modèle d'appartement, vous limiterez le jeu potentiel de conteneurs dans lesquels votre contrôle peut être utilisé.  
  
 Activer le threading de modèle d'appartement est facile pour la plupart des contrôles, notamment s'ils ont peu ou pas de données partagées.  
  
## Protéger les données partagées  
 Si votre contrôle utilise des données partagées, telles qu'une variable membre statique, l'accès à ces données doivent être protégées par une section critique pour éviter que plusieurs threads modifient les données en même temps.  Pour installer une section critique à cet effet, déclarez une variable membre statique de la classe `CCriticalSection` dans la classe de votre contrôle.  Utilisez les fonctions membres `Lock` et  **Déverrouiller** de cet objet de section critique là où le code accède aux données partagées.  
  
 Considérons, par exemple, une classe de contrôle qui doit contenir une chaîne partagée par toutes les instances.  Cette chaîne peut être maintenue dans une variable membre statique et être protégée par une section critique.  La déclaration de classe de contrôle contient les éléments suivants :  
  
```  
class CSampleCtrl : public COleControl  
{  
    ...  
    static CString _strShared;  
    static CCriticalSection _critSect;  
};  
```  
  
 L'implémentation de la classe comprend des définitions de ces variables :  
  
```  
int CString CSampleCtrl::_strShared;  
CCriticalSection CSampleCtrl::_critSect;  
```  
  
 L'accès au membre statique `_strShared` peut ensuite être protégé par la section critique :  
  
```  
void CSampleCtrl::SomeMethod()  
{  
    _critSect.Lock();  
    if (_strShared.Empty())  
        _strShared = "<text>";  
    _critSect.Unlock();  
    ...  
}  
```  
  
## Stocker un contrôle Modèle\-Appartement\-Compatible  
 Les contrôles qui prennent en charge le threading de modèle d'appartement doivent indiquer cette capacité dans le Registre, en ajoutant la valeur nommée « ThreadingModel » avec la valeur « Apartment » dans leur entrée de Registre ID de classe sous la clé  *ID de classe*\/**InprocServer32**.  Pour empêcher que cette clé soit automatiquement inscrite pour votre contrôle, passez l'indicateur `afxRegApartmentThreading` dans le sixième paramètre de `AfxOleRegisterControlClass`:  
  
```  
BOOL CSampleCtrl::CSampleCtrlFactory::UpdateRegistry(BOOL bRegister)  
{  
    if (bRegister)  
        return AfxOleRegisterControlClass(  
            AfxGetInstanceHandle(),  
            m_clsid,  
            m_lpszProgID,  
            IDS_SAMPLE,  
            IDB_SAMPLE,  
            afxRegApartmentThreading,  
            _dwSampleOleMisc,  
            _tlid,  
            _wVerMajor,  
            _wVerMinor);  
    else  
        return AfxOleUnregisterClass(m_clsid, m_lpszProgID);  
}  
```  
  
 Si votre projet de contrôle est généré par ControlWizard dans la version 4.1 de Visual C\+\+ ou une version ultérieure, cet indicateur est déjà présent dans votre code.  Aucune modification n'est nécessaire pour stocker le modèle de thread.  
  
 Si le projet a été généré par une version précédente de ControlWizard, votre code existant a une valeur booléenne comme sixième paramètre.  Si le paramètre existant est TRUE, modifiez\-le en  `afxRegInsertable | afxRegApartmentThreading`.  Si le paramètre existant est FALSE, modifiez\-le en  `afxRegApartmentThreading`.  
  
 Si votre contrôle ne respecte pas les règles pour le threading de modèle mode, vous ne devez pas passer `afxRegApartmentThreading` dans ce paramètre.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)