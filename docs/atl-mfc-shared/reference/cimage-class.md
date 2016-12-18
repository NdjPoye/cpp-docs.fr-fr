---
title: "CImage Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CImage"
  - "ATL.CImage"
  - "ATL::CImage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .gif, ATL and MFC support"
  - "bitmaps (C++), ATL and MFC support for"
  - "CImage class"
  - "fichiers gif, ATL and MFC support"
  - "images (C++), ATL and MFC support for"
  - "fichiers jpeg"
  - "fichiers PNG, ATL and MFC support"
  - "transparent color"
ms.assetid: 52861e3d-bf7e-481f-a240-90e88f76c490
caps.latest.revision: 20
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CImage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CImage` fournit la prise en charge de bitmap amélioré, notamment la possibilité de charger et d'enregistrer les images dans JPEG, GIF, BMP, et les formats de définition de données \(PNG\) PNG.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CImage  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CImage::CImage](../Topic/CImage::CImage.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CImage::AlphaBlend](../Topic/CImage::AlphaBlend.md)|Affiche les bitmaps qui ont des pixels transparents ou translucides.|  
|[CImage::Attach](../Topic/CImage::Attach.md)|Joint `HBITMAP` à un objet d' `CImage` .  Peut être utilisé avec des bitmaps de bitmap de section non fichier DIB ou de section du fichier DIB.|  
|[CImage::BitBlt](../Topic/CImage::BitBlt.md)|Copie une bitmap du contexte de périphérique source à ce contexte actuel de l'appareil.|  
|[CImage::Create](../Topic/CImage::Create.md)|Crée une image bitmap de section du fichier DIB et la attaché à l'objet précédemment construit d' `CImage` .|  
|[CImage::CreateEx](../Topic/CImage::CreateEx.md)|Crée une image bitmap de section du fichier DIB \(avec des paramètres supplémentaires\) et les attachés il à l'objet précédemment construit d' `CImage` .|  
|[CImage::Destroy](../Topic/CImage::Destroy.md)|Détache la bitmap de l'objet d' `CImage` et perd la bitmap.|  
|[CImage::Detach](../Topic/CImage::Detach.md)|Détache la bitmap d'un objet d' `CImage` .|  
|[CImage::Draw](../Topic/CImage::Draw.md)|Copie une bitmap d'un rectangle source dans un rectangle de destination.  **Draw** étire ou compresse la bitmap en fonction de les dimensions du rectangle de destination si nécessaire, et gère la fusion alpha et les couleurs transparentes.|  
|[CImage::GetBits](../Topic/CImage::GetBits.md)|Extrait un pointeur aux valeurs en pixels réelles de la bitmap.|  
|[CImage::GetBPP](../Topic/CImage::GetBPP.md)|Récupère les bits par pixel.|  
|[CImage::GetColorTable](../Topic/CImage::GetColorTable.md)|Récupère le rouge, vert, bleu valeurs de couleur de \(RGB\) d'une plage des entrées dans la table des couleurs.|  
|[CImage::GetDC](../Topic/CImage::GetDC.md)|Récupère le contexte de périphérique dans lequel la bitmap actuelle est sélectionnée.|  
|[CImage::GetExporterFilterString](../Topic/CImage::GetExporterFilterString.md)|Recherche les formats d'image disponibles et leurs descriptions.|  
|[CImage::GetHeight](../Topic/CImage::GetHeight.md)|Extrait la hauteur de l'image actuelle en pixels.|  
|[CImage::GetImporterFilterString](../Topic/CImage::GetImporterFilterString.md)|Recherche les formats d'image disponibles et leurs descriptions.|  
|[CImage::GetMaxColorTableEntries](../Topic/CImage::GetMaxColorTableEntries.md)|Récupère le nombre maximal d'entrées dans la table des couleurs.|  
|[CImage::GetPitch](../Topic/CImage::GetPitch.md)|Récupère le pas de l'image actuelle, en octets.|  
|[CImage::GetPixel](../Topic/CImage::GetPixel.md)|Extrait la couleur du pixel spécifié par *x* et *Y.*|  
|[CImage::GetPixelAddress](../Topic/CImage::GetPixelAddress.md)|Récupère l'adresse d'un pixel donné.|  
|[CImage::GetTransparentColor](../Topic/CImage::GetTransparentColor.md)|Extrait la position de la couleur transparente dans la table des couleurs.|  
|[CImage::GetWidth](../Topic/CImage::GetWidth.md)|Extrait la largeur de l'image actuelle en pixels.|  
|[CImage::IsDIBSection](../Topic/CImage::IsDIBSection.md)|Détermine si la bitmap attachée est une section du fichier DIB.|  
|[CImage::IsIndexed](../Topic/CImage::IsIndexed.md)|Indique que les couleurs d'une bitmap sont mappées à une palette indexée.|  
|[CImage::IsNull](../Topic/CImage::IsNull.md)|Indique si une bitmap source est actuellement chargé.|  
|[CImage::IsTransparencySupported](../Topic/CImage::IsTransparencySupported.md)|Indique si les bitmaps transparentes de l'application prend en charge et a été compilé pour Windows 2000 ou version ultérieure.|  
|[CImage::Load](../Topic/CImage::Load.md)|Charge une image à partir de le fichier spécifié.|  
|[CImage::LoadFromResource](../Topic/CImage::LoadFromResource.md)|Charge une image de la ressource spécifiée.|  
|[CImage::MaskBlt](../Topic/CImage::MaskBlt.md)|Combine des données couleur de la source et les bitmaps de destination à l'aide de le masque et l'opération raster spécifiés.|  
|[CImage::PlgBlt](../Topic/CImage::PlgBlt.md)|Exécute un transfert par bloc de bits d'un rectangle dans un contexte du périphérique source dans un parallélogramme dans un contexte de périphérique de destination.|  
|[CImage::ReleaseDC](../Topic/CImage::ReleaseDC.md)|Libère le contexte de périphérique qui a été récupéré avec [CImage::GetDC](../Topic/CImage::GetDC.md).|  
|[CImage::ReleaseGDIPlus](../Topic/CImage::ReleaseGDIPlus.md)|Libère les ressources utilisées par GDI\+.  Doit être appelé pour libérer les ressources créées par un objet global d' `CImage` .|  
|[CImage::Save](../Topic/CImage::Save.md)|Enregistre une image en tant que type spécifié.  **Enregistrer** impossible de spécifier des options d'image.|  
|[CImage::SetColorTable](../Topic/CImage::SetColorTable.md)|Définit le rouge, vert, les valeurs de couleur du bleu RVB\) dans une plage des entrées dans la table des couleurs de la section du fichier DIB.|  
|[CImage::SetPixel](../Topic/CImage::SetPixel.md)|Définit le pixel aux coordonnées spécifiées à la couleur spécifiée.|  
|[CImage::SetPixelIndexed](../Topic/CImage::SetPixelIndexed.md)|Définit le pixel aux coordonnées spécifiées à la couleur à l'index spécifié de la palette.|  
|[CImage::SetPixelRGB](../Topic/CImage::SetPixelRGB.md)|Définit le pixel aux coordonnées spécifiées spécifié au rouge, vert, bleu valeur de \(RGB\).|  
|[CImage::SetTransparentColor](../Topic/CImage::SetTransparentColor.md)|Définit l'index de la couleur à traiter comme transparent.  Une seule couleur dans une palette peut être transparente.|  
|[CImage::StretchBlt](../Topic/CImage::StretchBlt.md)|Copie une bitmap d'un rectangle source dans un rectangle de destination, d'étirement ou comprimant la bitmap en fonction de les dimensions du rectangle de destination, si nécessaire.|  
|[CImage::TransparentBlt](../Topic/CImage::TransparentBlt.md)|Copie une bitmap avec la couleur transparente du contexte de périphérique source à ce contexte actuel de l'appareil.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CImage::operator HBITMAP](../Topic/CImage::operator%20HBITMAP.md)|Retourne le handle de fenêtre attaché à l'objet d' `CImage` .|  
  
## Notes  
 `CImage` prend les bitmaps qui sont des sections de \(DIB\) .dib ou pas ; toutefois, vous pouvez utiliser [Create](../Topic/CImage::Create.md) ou [CImage::Load](../Topic/CImage::Load.md) avec uniquement des sections du fichier DIB.  Vous pouvez lier une image bitmap de section non fichier DIB à un objet d' `CImage` à l'aide de [Attachement](../Topic/CImage::Attach.md), mais en revanche vous ne pouvez pas utiliser les méthodes suivantes pour `CImage` , qui prennent uniquement en charge les bitmaps de section du fichier DIB :  
  
-   [GetBits](../Topic/CImage::GetBits.md)  
  
-   [GetColorTable](../Topic/CImage::GetColorTable.md)  
  
-   [GetMaxColorTableEntries](../Topic/CImage::GetMaxColorTableEntries.md)  
  
-   [GetPitch](../Topic/CImage::GetPitch.md)  
  
-   [GetPixelAddress](../Topic/CImage::GetPixelAddress.md)  
  
-   [IsIndexed](../Topic/CImage::IsIndexed.md)  
  
-   [SetColorTable](../Topic/CImage::SetColorTable.md)  
  
 Pour déterminer si une bitmap attachée est une section du fichier DIB, appelez [IsDibSection](../Topic/CImage::IsDIBSection.md)**.**  
  
> [!NOTE]
>  **Note** dans Visual Studio .NET 2003, cette classe contient le nombre d'objets d' `CImage` créé.  Chaque fois que le nombre accède à 0, la fonction [GdiplusShutdown](_gdiplus_func_gdiplusshutdown_) est automatiquement appelée pour libérer les ressources utilisées par GDI\+.  Cela garantit que tous les objets d' `CImage` créés directement ou indirectement par les DLL sont encore détruits correctement et que **GdiplusShutdown** n'est pas appelé d' `DllMain`.  
  
> [!NOTE]
>  Utilisation d'objets globaux d' `CImage` dans une DLL n'est pas recommandé.  Si vous devez utiliser un objet global d' `CImage` dans une DLL, appelez [CImage::ReleaseGDIPlus](../Topic/CImage::ReleaseGDIPlus.md) pour libérer explicitement les ressources utilisées par GDI\+.  
  
 `CImage` ne peut pas être sélectionné à nouveau [CDC](../../mfc/reference/cdc-class.md).  `CImage` crée son propre **HDC** pour l'image.  Étant donné qu' `HBITMAP` peut être sélectionné dans un **HDC** à la fois, `HBITMAP` associé à `CImage` ne peut pas être sélectionné dans un autre **HDC**.  Si vous avez besoin d' `CDC`, extrayez **HDC** d' `CImage` et donnez le à [CDC::FromHandle](../Topic/CDC::FromHandle.md).  
  
## Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#70](../../atl-mfc-shared/codesnippet/CPP/cimage-class_1.cpp)]  
  
 Lorsque vous utilisez `CImage` dans un projet MFC, notez que les fonctions membres dans votre projet attendent un pointeur vers un objet de [CBitmap](../../mfc/reference/cbitmap-class.md) .  Si vous souhaitez utiliser `CImage` avec une telle fonction, comme [CMenu::AppendMenu](../Topic/CMenu::AppendMenu.md), l'utilisation [CBitmap::FromHandle](../Topic/CBitmap::FromHandle.md), le passer votre `CImage``HBITMAP`, et utiliser `CBitmap*`retourné.  
  
## Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#71](../../atl-mfc-shared/codesnippet/CPP/cimage-class_2.cpp)]  
  
 Par `CImage`, vous avez accès aux bits réels d'une section du fichier DIB.  Vous pouvez utiliser un objet d' `CImage` partout où vous avez utilisé précédemment Win32 HBITMAP ou la section du fichier DIB.  
  
> [!NOTE]
>  Les méthodes suivantes pour `CImage` ont des limitations sur leur utilisation :  
  
|Méthode|Limitation|  
|-------------|----------------|  
|[PlgBlt](../Topic/CImage::PlgBlt.md)|Fonctionne uniquement avec Windows NT 4,0 ou version ultérieure.  Ne fonctionnera pas aux applications qui s'exécutent sur Windows 95\/98 ou version ultérieure.|  
|[MaskBlt](../Topic/CImage::MaskBlt.md)|Fonctionne uniquement avec Windows NT 4,0 ou version ultérieure.  Ne fonctionnera pas aux applications qui s'exécutent sur Windows 95\/98 ou version ultérieure.|  
|[AlphaBlend](../Topic/CImage::AlphaBlend.md)|Fonctionne uniquement avec Windows 2000, Windows 98, et les systèmes ultérieurs.|  
|[TransparentBlt](../Topic/CImage::TransparentBlt.md)|Fonctionne uniquement avec Windows 2000, Windows 98, et les systèmes ultérieurs.|  
|[Tracez](../Topic/CImage::Draw.md)|Prend en charge la transparence uniquement avec Windows 2000, Windows 98, et les systèmes ultérieurs.|  
  
 Consultez [Limitations de CImage aux systèmes d'exploitation antérieurs](../../mfc/cimage-limitations-with-earlier-operating-systems.md) pour plus d'informations sur les restrictions sur les ces méthodes.  
  
 Vous pouvez utiliser `CImage` MFC ou ATL.  
  
> [!NOTE]
>  Lorsque vous créez un projet à `CImage`, vous devez définir `CString` avant d'inclure `atlimage.h`.  Si votre projet utilise ATL sans MFC, incluez `atlstr.h` avant d'inclure `atlimage.h`.  Si votre projet utilise MFC \(ou s'il s'agit d'un projet ATL avec la prise en charge MFC\), incluez `afxstr.h` avant d'inclure `atlimage.h`.  
>   
>  De même, vous devez inclure `atlimage.h` avant d'inclure `atlimpl.cpp`.  Pour ce faire facilement, incluez `atlimage.h` dans votre `stdafx.h`.  
  
## Configuration requise  
 **Header:** atlimage.h  
  
## Voir aussi  
 [Exemple MMXSwarm](../../top/visual-cpp-samples.md)   
 [Exemple SimpleImage](../../top/visual-cpp-samples.md)   
 [Device\-Independent Bitmaps](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   
 [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)