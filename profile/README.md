## ABOUT

RETROJ2ME 是一個規整自我封裝程式碼的 Organization。

這裡的封裝，是指對一些 J2ME API 規範互相『翻譯』令其彼此互相相容。

本組織的任何更新均由個人的興趣決定。


## Core

### Docomo Core（DoJa/Star）

**[DoJa-to-MIDP-Core](https://github.com/RetroJ2ME/DoJa-to-MIDP-Core)**  
在個人的理解範圍內，對翻譯為 MIDP 的 DoJa API 進行了深度最佳化。

**[MLD PLyaer](https://github.com/Magstic/MLD_Player)**  
個人的一個獨立專案，專用於解碼 Docomo 的 MLD 旋律和採樣，它負責將 MLD 轉換為 MIDI 和 WAV，以供 MIDP 調用。


### Softbank Core（JSCL/VSCL/MEXA）

工事中……


### Willcom Core（AIR EDGE）

工事中……


### SKT Core（SK-VM）

工事中……


## Wrapper

## Docomo

| 作品 | 平臺 | 效能 | 地址 |
| :-- | :-- | :-- | :-- |
| 魔界塔士 Sa·Ga | DoJa | 真機，Heap 8MB | [GitHub](https://github.com/RetroJ2ME/SaGa_MIDP_Wrapper) |
| ワルキューレの栄光 | DoJa | 真機，Heap 8MB | [GitHub](https://github.com/RetroJ2ME/Valkyrie_MIDP_Wrapper) |
| 聖劍傳說 ～FF外傳～ | DoJa | 真機，Heap 2MB | [GitHub](https://github.com/RetroJ2ME/Mana_MIDP_Wrapper) |
| その兎、暴走。 | DoJa | 模擬器 | [GitHub](https://github.com/RetroJ2ME/Usatei_MIDP_Wrapper) |


## Technical 

圖是簡單的，但足以能一窺我的整套工作流。

題外話，毫不謙遜的說，這個架構經我手工設計，迭代數月。

即便程式碼是 Vibe，我也希望它能夠得到應有的尊重，而不是被所謂『古法至上』的偏見貶為垃圾。

```mermaid
flowchart TB
    A["原始遊戲資產"]

    subgraph FRAMEWORK["Runtime Wrapper Framework"]
        direction LR
        B["通用封裝程式"]
        C["專屬封裝程式"]
        D["音頻引擎"]
    end

    E["Java 編譯與整合"]
    S["MIDP / CLDC API Stub"]
    P["ProGuard"]
    F["MIDP 應用程式"]

    A --> B
    A --> C
    A --> D

    B --> E
    C --> E
    D --> E

    S -.->|編譯期依賴| E

    E --> P --> F

    classDef asset fill:#1E293B,stroke:#64748B,color:#FFFFFF,stroke-width:1.5px
    classDef module fill:#EFF6FF,stroke:#93C5FD,color:#1E40AF,stroke-width:1.5px
    classDef build fill:#F1F5F9,stroke:#94A3B8,color:#334155,stroke-width:1.5px
    classDef output fill:#0F766E,stroke:#115E59,color:#FFFFFF,stroke-width:1.5px

    class A asset
    class B,C,D module
    class E,S,P build
    class F output

    style FRAMEWORK fill:transparent,stroke:#94A3B8,stroke-width:1px,stroke-dasharray:5 4
    linkStyle default stroke:#94A3B8,stroke-width:1.5px
```

## License

RetroJ2ME 各專案的原創程式碼依其所屬 Repository 中標示的授權條款提供。

若有採用 GNU General Public License version 3.0 的 Repository，其修改、編譯與重新散布均須遵守許可協議。

任何個人或第三方平台重新散布包含 RetroJ2ME GPLv3 程式碼的預編譯 JAR 檔案時，均須履行適用的 GPLv3 義務，包括：

- 向接收者提供 GPLv3 授權條款全文。
- 保留原有的著作權、授權及免責聲明。
- 依 GPLv3 第 6 節提供對應原始碼的取得方式。
- 如有修改受 GPLv3 保護的程式碼，須依授權條款標示修改資訊。

**第三方遊戲內容不屬於 RetroJ2ME 的 GPLv3 授權範圍**，原始遊戲的程式碼、美術、音效、音樂、商標及其他素材，其權利仍歸各自權利人所有。

RetroJ2ME 的開源授權不構成對這些內容的再散布許可。

相關授權條件請參閱各 Repository 的 `LICENSE` 檔案及 [GNU GPLv3 官方全文](https://www.gnu.org/licenses/gpl-3.0.html)。


## WARN

一些『慷他人之慨的宵小之輩』已經嚴重觸及個人底線。

重新散布本 Organization 中採用 GPLv3 的程式碼或預編譯 JAR 時，請遵守上方 License 章節及所屬 Repository 的授權條款。

為了以儆效尤，震懾宵小，本 Organization 計劃參考 [FFmpeg 曾採用的 Hall of Shame 模式](https://ffmpeg.org/pipermail/ffmpeg-devel/2008-March/052760.html)，建立公開的違規散布紀錄。

對於經查證、聯絡並警告後，仍拒絕補正或持續違規散布的個人或平台，將在此列出可核對的事實與處理進度。

最終進度将連結至 [Hall of Shame](https://github.com/RetroJ2ME/Hall-of-Shame) Repository。

---

<div align="center">

<sub>Magstic 2026</sub>

</div>
