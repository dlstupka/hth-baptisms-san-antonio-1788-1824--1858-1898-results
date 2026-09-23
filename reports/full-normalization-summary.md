# Full normalization summary

<a id="table-of-contents"></a>

<details open>
<summary><strong>Navigation</strong></summary>

- [Audit status](#audit-status)
- [Normalization result chain](#normalization-result-chain)
- [Canonical Build Evidence ledger](#canonical-build-evidence-ledger)
- [Cache and release lifecycle](#cache-and-release-lifecycle)
  - [Cleanup-eligible releases (3)](#cleanup-eligible-releases-3)
- [Engineering recommendations](#engineering-recommendations)
- [Engineering reference](#engineering-reference)

</details>


> Audit report generated exclusively from persisted Canonical Build Evidence, normalization manifests, and the resource-lifecycle ledger. No normalization pixels or domain results were recomputed.

<a id="audit-status"></a>
<details open>
<summary><h2>Audit status</h2></summary>

- Status: **COMPLETE**
- Authoritative normalization CBE stages: `28/28`
- Durable transformation manifests: `7/7` valid
- Resource lifecycle ledger: `valid`
- Results snapshot: [`0ab47741834c33cf8570818f93a7e4cb95fa59d1`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/commit/0ab47741834c33cf8570818f93a7e4cb95fa59d1)
- Report Writer run: [workflow run](https://github.com/dlstupka/hth/actions/runs/35806954384)

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="normalization-result-chain"></a>
<details open>
<summary><h2>Normalization result chain</h2></summary>

| Stage | Status | Method / policy | Pages | Corrected | Preserved | Result identity |
|---|---:|---|---:|---:|---:|---|
| Canonical crop/orientation | `complete` | `axis-aligned-detector-envelope-v1+hough-lines-conservative-v1` | `929` | `12` | `917` | [`d0fb2998d1cfcef91f6c6469ff9223184243aedebb85bf1746ab13b8c1d26e80`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/normalization-manifest.json) |
| Photometric | `complete` | `background-division-50` | `929` | `87` | `842` | [`7b07faf833091821cd98cf614b113dcc23aaf7b98298fc1a5c06105ccbb5a109`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/photometric-integration/photometric-normalization-manifest.json) |
| Tonal | `complete` | `none` | `929` | `0` | `929` | [`c2f5ae76936d37fa42496bc25e8ee6ed65ed6631de78f4a4700d717399aa9138`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/tonal-integration/tonal-normalization-manifest.json) |
| Chromatic | `complete` | `none` | `929` | `0` | `929` | [`8829f6f3940a4b704ee391ddfcca78e78e3ba1006654252bac781020a2134219`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/chromatic-integration/chromatic-normalization-manifest.json) |
| Denoising | `complete` | `none` | `929` | `0` | `929` | [`094ac70718c060d065e001a2df43fd064d22f5529c88502256d07cdd1b2a73dc`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/denoising-integration/denoising-normalization-manifest.json) |
| Sharpening | `complete` | `none` | `929` | `0` | `929` | [`d53dcc858a77ccec5a9ec51690a9b6e21cf9833e6be2520d53159465e95ea91f`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/sharpening-integration/sharpening-normalization-manifest.json) |
| Binarization | `complete` | `none` | `929` | `0` | `929` | [`b1881012e53c85ff792a9c65ac2cd9cdfa8c7e74e3566c730e087a58a626aca4`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/binarization-integration/binarization-normalization-manifest.json) |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="canonical-build-evidence-ledger"></a>
<details>
<summary><h2>Canonical Build Evidence ledger</h2></summary>

| Stage scope | State | Activity | Pages | Effective build | Canonical result | Source release utilized | Evidence |
|---|---:|---|---:|---|---|---|---|
| `hth-normalization` | `authoritative` | `EXECUTED` | `929` | `189331a8a048a0fffe60d01f2779841123e47ea54877e2be80f038825acaaf73` | `23aa350a1aebe31cc250ea41f4914f246ec74712799236557671b506e4a9194d` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@555e935db9df90c0ea451622dee8f597a11e6ffc190cf34d73a06ea547b379b5` | [`normalization/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/canonical-build-evidence.json) |
| `hth-photometric-integration` | `authoritative` | `EXECUTED` | `929` | `e5ff0faf9a483f7130cc59797d8d4c67afe301afcdcf67b31ca601ce12b914cd` | `4091c531289c856862a73cfdb86c2074ab9ce691808715c86d8fcdcf4d36ab7f` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@a485dd92959c6290e792214fcbd062b79132e668678fccd980b7d0a15e04d2ab` | [`normalization/photometric-integration/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/photometric-integration/canonical-build-evidence.json) |
| `hth-tonal-assessment` | `authoritative` | `EXECUTED` | `929` | `b244df44bb5ba61f5b5e3fab41e902b9d75e5ed10ad950a78df213d2c86f8993` | `b70efef9ca06774529d5127fb6109a3b071e5574ab4bad865cc7ee19c80a748d` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-PHOTOMETRIC-7b07faf833091821cd98cf614b113dcc23aaf7b98298fc1a5c06105ccbb5a109` | [`normalization/tonal/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/tonal/canonical-build-evidence.json) |
| `hth-tonal-method-assessment` | `authoritative` | `EXECUTED` | `138` | `ca1d2663ca0fc27ce415820cc7a1499f29a2966aa463397e495679c40beab584` | `fe559b728d140c772ba7b1fe1d8231494c7fbd4acc4923637962e1a5642a632c` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-PHOTOMETRIC-7b07faf833091821cd98cf614b113dcc23aaf7b98298fc1a5c06105ccbb5a109` | [`normalization/tonal-methods/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/tonal-methods/canonical-build-evidence.json) |
| `hth-tonal-validation` | `authoritative` | `EXECUTED` | `535` | `6b0ea41efcf69e07ba990a5c799df7133f21af260cff5ae563c53353a20b12d0` | `04908a50ef0da814e9bb531aa0912c3df2e93bbd97dd1ccfa5a74dd7676da33a` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-PHOTOMETRIC-7b07faf833091821cd98cf614b113dcc23aaf7b98298fc1a5c06105ccbb5a109` | [`normalization/tonal-validation/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/tonal-validation/canonical-build-evidence.json) |
| `hth-tonal-integration` | `authoritative` | `EXECUTED` | `929` | `5ef234331fc3e59e40a4839f9fd89b0db94edfe86fd032db3772c358f5a97098` | `167d825cb8e4bad53d1501cbaf6cbb51041a4939f2d917edff8df8020c8a6a86` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-PHOTOMETRIC-7b07faf833091821cd98cf614b113dcc23aaf7b98298fc1a5c06105ccbb5a109` | [`normalization/tonal-integration/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/tonal-integration/canonical-build-evidence.json) |
| `hth-chromatic-assessment` | `authoritative` | `EXECUTED` | `929` | `310be201f777abe21124f0eda4261d19be069138ac9084d6ae148556f94b1ba7` | `53167314c2203d5232885db96440427dd11c2eaa131e80d585d112111615bdff` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-TONAL-c2f5ae76936d37fa42496bc25e8ee6ed65ed6631de78f4a4700d717399aa9138` | [`normalization/chromatic/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/chromatic/canonical-build-evidence.json) |
| `hth-chromatic-method-assessment` | `authoritative` | `EXECUTED` | `0` | `260e866a41470a30c2e38af932602d572fce2787e342ffd933a9e863e449cbaa` | `d0ccca577c1809f4a54511db68639f4ba255a31ae435b4f8f06e53a08a0f26d6` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-TONAL-c2f5ae76936d37fa42496bc25e8ee6ed65ed6631de78f4a4700d717399aa9138` | [`normalization/chromatic-methods/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/chromatic-methods/canonical-build-evidence.json) |
| `hth-chromatic-validation` | `authoritative` | `EXECUTED` | `0` | `e231addda6d04334e5c0aa0bd6d960db20c59aa4353763879b4b87d451d83128` | `a4ae7938b12b3bd572a843a4f30857870b34c558bdc420a8ad8657985dda3348` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-TONAL-c2f5ae76936d37fa42496bc25e8ee6ed65ed6631de78f4a4700d717399aa9138` | [`normalization/chromatic-validation/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/chromatic-validation/canonical-build-evidence.json) |
| `hth-chromatic-integration` | `authoritative` | `EXECUTED` | `929` | `16551ac7cb10828a957480228c868948d124c19faf521c9002fae71b56a5b4b4` | `ee5c0a4ddd47a9e651f589b2237cbb5e5016b7f818abcb9f2658963a3d78a030` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-TONAL-c2f5ae76936d37fa42496bc25e8ee6ed65ed6631de78f4a4700d717399aa9138` | [`normalization/chromatic-integration/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/chromatic-integration/canonical-build-evidence.json) |
| `hth-denoising-assessment` | `authoritative` | `EXECUTED` | `929` | `48e929e9e0e398ad5408a7c4c69a4813e7b3e014f96199d855ebbd2405f42304` | `7d72c13362cf69496c8cc74fe90a2f509ea7c26aa1506abd5abb1ed031b2cd6b` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-CHROMATIC-8829f6f3940a4b704ee391ddfcca78e78e3ba1006654252bac781020a2134219` | [`normalization/denoising/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/denoising/canonical-build-evidence.json) |
| `hth-denoising-method-assessment` | `authoritative` | `EXECUTED` | `185` | `77ceae41b44b8e37f4b6bb24ebae4f1eed9d8502088393b4105fe8d1e2626a98` | `4719aea8ac8983a649a0518437837a0b1009101b8c620821d01a9fb54e3fe520` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-CHROMATIC-8829f6f3940a4b704ee391ddfcca78e78e3ba1006654252bac781020a2134219` | [`normalization/denoising-methods/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/denoising-methods/canonical-build-evidence.json) |
| `hth-denoising-validation` | `authoritative` | `EXECUTED` | `742` | `d7b42fd5e8a0c375aebb125a0f1c13020aa357d0863dfb386a7151cfe9e39c74` | `40c3e1f2c7ed0eb17d4499d4b49c513a706fb868a435afa5b041930179309ad4` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-CHROMATIC-8829f6f3940a4b704ee391ddfcca78e78e3ba1006654252bac781020a2134219` | [`normalization/denoising-validation/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/denoising-validation/canonical-build-evidence.json) |
| `hth-denoising-integration` | `authoritative` | `EXECUTED` | `929` | `3a5c43180655e351e667bb6a67d1e88a6208baefcecd369b65e38580cab9eaae` | `aab6bb48c4dce10b15bb8f2a909868dcd702170ec6ef50b7854cd6ff9ab1bba3` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-CHROMATIC-8829f6f3940a4b704ee391ddfcca78e78e3ba1006654252bac781020a2134219` | [`normalization/denoising-integration/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/denoising-integration/canonical-build-evidence.json) |
| `hth-sharpening-assessment` | `authoritative` | `EXECUTED` | `929` | `4fe23616696bec0ee4f8da3b98f538f4f9a21b8148998d6a1314ffc8eee669df` | `7b6ee1e7c702621e4bdd82d4248e416b0c825444225d47b3c8c80d3882af85ed` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-DENOISING-094ac70718c060d065e001a2df43fd064d22f5529c88502256d07cdd1b2a73dc` | [`normalization/sharpening/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/sharpening/canonical-build-evidence.json) |
| `hth-sharpening-method-assessment` | `authoritative` | `EXECUTED` | `1` | `4608d5cf9072c675dcced19424e3e1cb7c513fc00dcaae8feb33690649c93b7b` | `1d5a12390a43b3963cfc1aa12f9c0bc9f91b86bdd295e39b99c7536d624a4b16` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-DENOISING-094ac70718c060d065e001a2df43fd064d22f5529c88502256d07cdd1b2a73dc` | [`normalization/sharpening-methods/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/sharpening-methods/canonical-build-evidence.json) |
| `hth-sharpening-validation` | `authoritative` | `EXECUTED` | `1` | `cf070cddbff62b344521eae508a04c9d4bef05a85dac7aecd360189a08fdd9db` | `f75cb213f63553248cbddad94de5738bedfea1cdb88edc6377f8bafef35c91ee` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-DENOISING-094ac70718c060d065e001a2df43fd064d22f5529c88502256d07cdd1b2a73dc` | [`normalization/sharpening-validation/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/sharpening-validation/canonical-build-evidence.json) |
| `hth-sharpening-integration` | `authoritative` | `EXECUTED` | `929` | `aca13f3688e20331c2b7f0c17c1cc05854d6ce5e3a6f121da215073ae55bfce7` | `e820b4bc5d667190630d54509686e4767506024e01363786966a2f6e02de79d6` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-DENOISING-094ac70718c060d065e001a2df43fd064d22f5529c88502256d07cdd1b2a73dc` | [`normalization/sharpening-integration/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/sharpening-integration/canonical-build-evidence.json) |
| `hth-binarization-assessment` | `authoritative` | `EXECUTED` | `929` | `d1d23fede15f92cfd9e0d1ff71a3d2bf4ae7cf11f20e064b341457376b89efd8` | `f93d564bbac5179a14378ac4701b81906dda71fbe70eb8135d8f7480e847b0d5` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-SHARPENING-d53dcc858a77ccec5a9ec51690a9b6e21cf9833e6be2520d53159465e95ea91f` | [`normalization/binarization/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/binarization/canonical-build-evidence.json) |
| `hth-binarization-method-assessment` | `authoritative` | `EXECUTED` | `185` | `d78c875fd831fb9caf12db87df4c3a8f8578301282fac2be18e57992e53f77e0` | `b4ed9120a601083a1a6f318b1b114bf08cf437c190190444cbada4bd3eceafad` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-SHARPENING-d53dcc858a77ccec5a9ec51690a9b6e21cf9833e6be2520d53159465e95ea91f` | [`normalization/binarization-methods/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/binarization-methods/canonical-build-evidence.json) |
| `hth-binarization-validation` | `authoritative` | `EXECUTED` | `738` | `26275b8823f9481a2de7a246603a22ec71ae6c5f423f98286d8533ecc4ee7672` | `22d3232d4e768d0b4947f2db2862e332298afbb59bb56d86e0a2c43dd976b273` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-SHARPENING-d53dcc858a77ccec5a9ec51690a9b6e21cf9833e6be2520d53159465e95ea91f` | [`normalization/binarization-validation/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/binarization-validation/canonical-build-evidence.json) |
| `hth-binarization-integration` | `authoritative` | `EXECUTED` | `929` | `085b500c1c06a56efcc9c032bb7a2c34854b47d61597fcd9d7e5975c4a868319` | `346697ca343d48944fa3fa9a7318b2f2e501fed1aa819dfe72a27880e4bb0b41` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-SHARPENING-d53dcc858a77ccec5a9ec51690a9b6e21cf9833e6be2520d53159465e95ea91f` | [`normalization/binarization-integration/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/binarization-integration/canonical-build-evidence.json) |
| `hth-crop-framing-assessment` | `authoritative` | `EXECUTED` | `18` | `f578b99766df8910d7446073fb60d812e8b3331c77df79fa9bdb55c38d11b8d7` | `9d011c44b4bbb517f7b2ee4a53a73baec2c1ec147b7512b96605b5fc5e3dbbab` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898@HTH-GOLDEN-0002` | [`normalization/crop-framing/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/crop-framing/canonical-build-evidence.json) |
| `hth-orientation-deskew-assessment` | `authoritative` | `EXECUTED` | `79` | `770a461f9fafa86c119a9f0d51f7020cbd6351e61f8e316dc4414af734d47d84` | `54f5cfb5ba4faf8dbe714f30fd377358d95e1811c7d5b4a1135845f0c0934b54` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@2e8ab1f37673af88d32aac59897010d1cf3689682b924778f3bf287a0ad805e1` | [`normalization/orientation-deskew/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/orientation-deskew/canonical-build-evidence.json) |
| `hth-perspective-assessment` | `authoritative` | `EXECUTED` | `79` | `ef3fddb2c377208fda01b4337de0c3fc92f5e1ed9fadaa94c2e680c7ea68c6a0` | `c6460089390b5fc834e95de298d8327030fcfec317913cfd5ea989cb488f9e45` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@189331a8a048a0fffe60d01f2779841123e47ea54877e2be80f038825acaaf73` | [`normalization/perspective/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/perspective/canonical-build-evidence.json) |
| `hth-photometric-assessment` | `authoritative` | `EXECUTED` | `79` | `8af10f6d959b28c2c1d473d01abfcbd1cdcdc4f97bb9ec674a7c7a44a031ea96` | `229fac924f8d4bf8309552ad22fb04a4bd4bc0e97595d584215343e610313c19` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@189331a8a048a0fffe60d01f2779841123e47ea54877e2be80f038825acaaf73` | [`normalization/photometric/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/photometric/canonical-build-evidence.json) |
| `hth-photometric-method-assessment` | `authoritative` | `EXECUTED` | `8` | `4b8e8ddae94054036d892d444413f315c6a7f25f85bee3003e8b38ba6d70515f` | `291089e8f3ba1ef134b5b8dd4c08edf2e39258c3e19f328b01568e5a68a00125` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@62bf9dd8c1a5f1835a961b7bcfb9d327b2bddcde1869740c01d2be8722b52dee` | [`normalization/photometric-methods/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/photometric-methods/canonical-build-evidence.json) |
| `hth-photometric-validation` | `authoritative` | `EXECUTED` | `921` | `e44a799ead34a02f98d95cadec60102c9a522fcedaafc0be96d81aedd5e6cb62` | `f5afb0a51d5b9b856805a9b1dd36d1c692a50d3be87fa11225117ae7d5bfac12` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@32f43540f1bf54e318963ab6c4af0aec7923272505a1c0e6d23def7c2a56734b` | [`normalization/photometric-validation/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/normalization/photometric-validation/canonical-build-evidence.json) |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="cache-and-release-lifecycle"></a>
<details open>
<summary><h2>Cache and release lifecycle</h2></summary>

- Resource state identity: [`9ff3ffabf94ab42dad11b83d8f8f83a7532feec829085e37ba31395cf6bb09d1`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/0ab47741834c33cf8570818f93a7e4cb95fa59d1/metadata/resource-lifecycle.json)
- Build records: `111`
- Cache elements: `111` total; `82` dirty; `0` cleanup-eligible
- Release elements: `52` total; `38` dirty; `3` cleanup-eligible
- Cleanup action: `none` — this is a provenance and eligibility report, not a deletion job.

[↑ Back to Navigation](#table-of-contents)

<a id="cleanup-eligible-releases-3"></a>
<details>
<summary><h3>Cleanup-eligible releases (3)</h3></summary>

| Release | Kind | Integrity | Lineage | Publication | Reason |
|---|---|---|---|---|---|
| `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-BINARIZATION-46d335fccbc91a8b268f118a4b83424617612ee648d899138c5c840d58056866` | `regular` | `unknown` | `superseded` | `not-latest` | `superseded-unreferenced-inventory-release` |
| `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-BINARIZATION-c8c610d97552426def0769e4af9ef8e4b1f528419e161d179e665aac2e877e02` | `regular` | `unknown` | `superseded` | `not-latest` | `superseded-unreferenced-inventory-release` |
| `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-SHARPENING-3940e97d99ae91c04975c0a2d16597cdfdcc394c1627f905ba3195132f240868` | `regular` | `unknown` | `superseded` | `not-latest` | `superseded-unreferenced-inventory-release` |

</details>

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="engineering-recommendations"></a>
<details open>
<summary><h2>Engineering recommendations</h2></summary>

- Review the `3` cleanup-eligible release(s) against retention policy before deletion; eligibility is recorded, but this report intentionally performs no cleanup.

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="engineering-reference"></a>
<details>
<summary><h2>Engineering reference</h2></summary>

- [Normalization design, provenance, policy, and operating guidance](https://github.com/dlstupka/hth/blob/c42bfa1c684d0b1b08306654c754de4c726c11de/docs/normalization.md)

</details>

[↑ Back to Navigation](#table-of-contents)
