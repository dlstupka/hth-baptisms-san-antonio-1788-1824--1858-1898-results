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
- Results snapshot: [`2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/commit/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b)
- Report Writer run: [workflow run](https://github.com/dlstupka/hth/actions/runs/35917390585)

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="normalization-result-chain"></a>
<details open>
<summary><h2>Normalization result chain</h2></summary>

| Stage | Status | Method / policy | Pages | Corrected | Preserved | Result identity |
|---|---:|---|---:|---:|---:|---|
| Canonical crop/orientation | `complete` | `axis-aligned-detector-envelope-v1+hough-lines-conservative-v1` | `929` | `12` | `917` | [`d0fb2998d1cfcef91f6c6469ff9223184243aedebb85bf1746ab13b8c1d26e80`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/normalization-manifest.json) |
| Photometric | `complete` | `background-division-50` | `929` | `87` | `842` | [`7b07faf833091821cd98cf614b113dcc23aaf7b98298fc1a5c06105ccbb5a109`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/photometric-integration/photometric-normalization-manifest.json) |
| Tonal | `complete` | `none` | `929` | `0` | `929` | [`ee25322d85649442f0346f75fbe4c4944925a4eaa23bf1d64838e158d1dba13d`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/tonal-integration/tonal-normalization-manifest.json) |
| Chromatic | `complete` | `none` | `929` | `0` | `929` | [`24606577b231c1140751648b6b751d454d57835d4c74d1dbdb833e43f64d9a8c`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/chromatic-integration/chromatic-normalization-manifest.json) |
| Denoising | `complete` | `none` | `929` | `0` | `929` | [`cb8d44356a75cb14eab58782cc33258773ff3a3ff4e0767eea55ea93f82fd587`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/denoising-integration/denoising-normalization-manifest.json) |
| Sharpening | `complete` | `none` | `929` | `0` | `929` | [`f2c905dca167dab495a86eb873dc078bbe1dc8a0431d26365510ec290e8ddea5`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/sharpening-integration/sharpening-normalization-manifest.json) |
| Binarization | `complete` | `none` | `929` | `0` | `929` | [`46d335fccbc91a8b268f118a4b83424617612ee648d899138c5c840d58056866`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/binarization-integration/binarization-normalization-manifest.json) |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="canonical-build-evidence-ledger"></a>
<details>
<summary><h2>Canonical Build Evidence ledger</h2></summary>

Recorded build activity describes when the authoritative result was created; it does not describe reuse in this report run. The reuse decision and reason are shown in each workflow's Canonical Build Evidence summary.

| Stage scope | State | Recorded build activity | Pages | Effective build | Canonical result | Source release utilized | Evidence |
|---|---:|---|---:|---|---|---|---|
| `hth-normalization` | `authoritative` | `EXECUTED` | `929` | `4d7d2198ea127d986dae18017258e1147269711c19a2eb07a6344b25ccf8bc69` | `110330a1f15d5c447e98bfc8355504052ca40bcbf09dbd1cee352946eab3510b` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@c665851bfe2e0303b5742a69b1b46314fca45dd82bf9933398f6bbcece4a5b44` | [`normalization/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/canonical-build-evidence.json) |
| `hth-photometric-integration` | `authoritative` | `EXECUTED` | `929` | `7a608ed8eff20020f1487eccac01afbb0effa2a55f4d317f31e58b076b9644f0` | `4091c531289c856862a73cfdb86c2074ab9ce691808715c86d8fcdcf4d36ab7f` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@a485dd92959c6290e792214fcbd062b79132e668678fccd980b7d0a15e04d2ab` | [`normalization/photometric-integration/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/photometric-integration/canonical-build-evidence.json) |
| `hth-tonal-assessment` | `authoritative` | `EXECUTED` | `929` | `b244df44bb5ba61f5b5e3fab41e902b9d75e5ed10ad950a78df213d2c86f8993` | `b70efef9ca06774529d5127fb6109a3b071e5574ab4bad865cc7ee19c80a748d` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-PHOTOMETRIC-7b07faf833091821cd98cf614b113dcc23aaf7b98298fc1a5c06105ccbb5a109` | [`normalization/tonal/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/tonal/canonical-build-evidence.json) |
| `hth-tonal-method-assessment` | `authoritative` | `EXECUTED` | `138` | `0efe04a1d2f587651325e46c9b6c0edecfa72d1b67ded130d1b118e25173b455` | `165ccf9e38a1aaec533c8e1b16590fa4a18c53b0ba129dbc41c25a0e8ab82d46` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-PHOTOMETRIC-7b07faf833091821cd98cf614b113dcc23aaf7b98298fc1a5c06105ccbb5a109` | [`normalization/tonal-methods/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/tonal-methods/canonical-build-evidence.json) |
| `hth-tonal-validation` | `authoritative` | `EXECUTED` | `535` | `44015ff89e231b3b1f3d579e34bcf9498c2fa41d59790747b3d5c395d5647170` | `2fa401b3386734198a25824883fec617f1625ca7a9d67e7ea3c96bc5c0e15bdd` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-PHOTOMETRIC-7b07faf833091821cd98cf614b113dcc23aaf7b98298fc1a5c06105ccbb5a109` | [`normalization/tonal-validation/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/tonal-validation/canonical-build-evidence.json) |
| `hth-tonal-integration` | `authoritative` | `EXECUTED` | `929` | `1afab5824a5a285437634348d534f4b2009d7bb1bd7091ed81d01b122594f1fe` | `b32672a2a8eb02c5a82a297f8c45bc47aaa72606d2c85f901ebd0a8582fea646` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-PHOTOMETRIC-7b07faf833091821cd98cf614b113dcc23aaf7b98298fc1a5c06105ccbb5a109` | [`normalization/tonal-integration/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/tonal-integration/canonical-build-evidence.json) |
| `hth-chromatic-assessment` | `authoritative` | `EXECUTED` | `929` | `fec89362641bd85aea86c84a6417b41e4e320cd34327fcb57a324ab962c0fe23` | `9b5d3e646c6ba14885d7d8f629f1a323923db70dd8d505188eaa517ddb6fcfe1` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-TONAL-ee25322d85649442f0346f75fbe4c4944925a4eaa23bf1d64838e158d1dba13d` | [`normalization/chromatic/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/chromatic/canonical-build-evidence.json) |
| `hth-chromatic-method-assessment` | `authoritative` | `EXECUTED` | `0` | `51a38d2bb59eeec9a8fa7cd9c215907ae3449f449e58dae184cfa21a99c6b784` | `1b6787121996d643819eddd28a747f945ea6207962bec345668f2323cac33c60` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-TONAL-ee25322d85649442f0346f75fbe4c4944925a4eaa23bf1d64838e158d1dba13d` | [`normalization/chromatic-methods/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/chromatic-methods/canonical-build-evidence.json) |
| `hth-chromatic-validation` | `authoritative` | `EXECUTED` | `0` | `dfed8b0440606eecd8fa1dd561968dbb4abdf88e76b70244614553a555846a81` | `42e0cde53872f5e5cded945e4c53c105be737b9456a857cd6e0101032ce1c0f3` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-TONAL-ee25322d85649442f0346f75fbe4c4944925a4eaa23bf1d64838e158d1dba13d` | [`normalization/chromatic-validation/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/chromatic-validation/canonical-build-evidence.json) |
| `hth-chromatic-integration` | `authoritative` | `EXECUTED` | `929` | `965e757754cee04da0c6b35a90c3e46f6bf7b29bd203ea1b3ff2927b83a61d47` | `a65a9003cf6ff9d59f27360bd37dc2758cfbc2413fe63fede2c44e3ef80681ba` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-TONAL-ee25322d85649442f0346f75fbe4c4944925a4eaa23bf1d64838e158d1dba13d` | [`normalization/chromatic-integration/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/chromatic-integration/canonical-build-evidence.json) |
| `hth-denoising-assessment` | `authoritative` | `EXECUTED` | `929` | `be26e70d1c41fd99de424d9e6cb4fa6ae5fda28b12bc689bcce786f105b1addc` | `91c32c85bbdcddd4378ce13a9a0bbef4aa72c46f543d6e8de33e24198b1cf235` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-CHROMATIC-24606577b231c1140751648b6b751d454d57835d4c74d1dbdb833e43f64d9a8c` | [`normalization/denoising/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/denoising/canonical-build-evidence.json) |
| `hth-denoising-method-assessment` | `authoritative` | `EXECUTED` | `185` | `6d4e1452b6d388a60f02621a03531a2245426ad3c4bb16231b75f5d953b16105` | `83889895bb9308fd8c5b04fa74746c3bb92da82344716a47d052ead28381f2aa` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-CHROMATIC-24606577b231c1140751648b6b751d454d57835d4c74d1dbdb833e43f64d9a8c` | [`normalization/denoising-methods/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/denoising-methods/canonical-build-evidence.json) |
| `hth-denoising-validation` | `authoritative` | `EXECUTED` | `742` | `946f3fc078f94d22baa54724c75c7bc9363ddfcc1a0e1fce49a3767241bd3e27` | `652cd09d303eec29d243e1dcf549f933b2d60224aa0b2d498104c7f59bcd0f03` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-CHROMATIC-24606577b231c1140751648b6b751d454d57835d4c74d1dbdb833e43f64d9a8c` | [`normalization/denoising-validation/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/denoising-validation/canonical-build-evidence.json) |
| `hth-denoising-integration` | `authoritative` | `EXECUTED` | `929` | `721b82664886bdb3c8e33988e55ff6f45dd1b4a7a1fe2b4aa09cddbe11f1b79a` | `dababfb26cf8d17b65b6902b9deba9b7d89ed3c7cd58e4350ac6b9094c6f849c` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-CHROMATIC-24606577b231c1140751648b6b751d454d57835d4c74d1dbdb833e43f64d9a8c` | [`normalization/denoising-integration/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/denoising-integration/canonical-build-evidence.json) |
| `hth-sharpening-assessment` | `authoritative` | `EXECUTED` | `929` | `702651f6978dfb69efdf0a6c49904ef21b6512827e0817e59cbbf9e63b94314c` | `2fe48dd56537c50f7214cb83ff76a4a84bdf2450e59d7a688b70397320ee5ded` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-DENOISING-cb8d44356a75cb14eab58782cc33258773ff3a3ff4e0767eea55ea93f82fd587` | [`normalization/sharpening/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/sharpening/canonical-build-evidence.json) |
| `hth-sharpening-method-assessment` | `authoritative` | `EXECUTED` | `1` | `36fdf9f95a45fdce2ea5ad5c978a337b44ba145ea064cdebbe5d985ecd988238` | `9bb6bb8efc833d527274f13e31180173b58f20e7a959e2ed261f573fee46dbe4` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-DENOISING-cb8d44356a75cb14eab58782cc33258773ff3a3ff4e0767eea55ea93f82fd587` | [`normalization/sharpening-methods/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/sharpening-methods/canonical-build-evidence.json) |
| `hth-sharpening-validation` | `authoritative` | `EXECUTED` | `1` | `fba10d63904da03d77052d127db7669b54b3cc7e9ef2711915a3d6f7e9a0d95f` | `957e2c0a7a40985189dc473470e6842a87c54b6c1fb2d0f23e8648c8769e3edf` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-DENOISING-cb8d44356a75cb14eab58782cc33258773ff3a3ff4e0767eea55ea93f82fd587` | [`normalization/sharpening-validation/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/sharpening-validation/canonical-build-evidence.json) |
| `hth-sharpening-integration` | `authoritative` | `EXECUTED` | `929` | `5e081d4cd8d45a839663089f7b33d3396b32835a80cd3327d2bea58eb745096d` | `094bb23bcf12fac8754f327a0cf630ccdf8f467feacf8e2e97621d3c5bd232ad` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-DENOISING-cb8d44356a75cb14eab58782cc33258773ff3a3ff4e0767eea55ea93f82fd587` | [`normalization/sharpening-integration/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/sharpening-integration/canonical-build-evidence.json) |
| `hth-binarization-assessment` | `authoritative` | `EXECUTED` | `929` | `6dd2341fa1c17c385194b8a927f444ad27aa031cab54cf6cdb3e08f0475eab6a` | `fa91013879d312474a5fce31dac72a460540eb6c6931d59971f56c5855713f2a` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-SHARPENING-f2c905dca167dab495a86eb873dc078bbe1dc8a0431d26365510ec290e8ddea5` | [`normalization/binarization/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/binarization/canonical-build-evidence.json) |
| `hth-binarization-method-assessment` | `authoritative` | `EXECUTED` | `185` | `c3c134016a10150163e758356e9c3804f3e51c7fea25faef8a753c83fb64b064` | `f40c9d371e96eb707ba9b7f0086902ce6cfcb636f140ebb8300c563f0687586d` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-SHARPENING-f2c905dca167dab495a86eb873dc078bbe1dc8a0431d26365510ec290e8ddea5` | [`normalization/binarization-methods/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/binarization-methods/canonical-build-evidence.json) |
| `hth-binarization-validation` | `authoritative` | `EXECUTED` | `738` | `7002ec346ed2a1253183a7a9967698530bb5bea9c86902e4d205fa373a17310e` | `451ccd43b668627d73e3d8536c911639ec8434c1feb3a6411c8ad914b778fb00` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-SHARPENING-f2c905dca167dab495a86eb873dc078bbe1dc8a0431d26365510ec290e8ddea5` | [`normalization/binarization-validation/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/binarization-validation/canonical-build-evidence.json) |
| `hth-binarization-integration` | `authoritative` | `EXECUTED` | `929` | `162c676313ffbbda2e540e5662eb7f85c6ad96f95d693303bf5225e067b50426` | `80540118682b293409cfbf0b10e24b06ec666164a9b296a7d065fcca7e77b3c5` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-SHARPENING-f2c905dca167dab495a86eb873dc078bbe1dc8a0431d26365510ec290e8ddea5` | [`normalization/binarization-integration/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/binarization-integration/canonical-build-evidence.json) |
| `hth-crop-framing-assessment` | `authoritative` | `EXECUTED` | `18` | `f578b99766df8910d7446073fb60d812e8b3331c77df79fa9bdb55c38d11b8d7` | `9d011c44b4bbb517f7b2ee4a53a73baec2c1ec147b7512b96605b5fc5e3dbbab` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898@HTH-GOLDEN-0002` | [`normalization/crop-framing/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/crop-framing/canonical-build-evidence.json) |
| `hth-orientation-deskew-assessment` | `authoritative` | `EXECUTED` | `79` | `577d08ee807bfdd58ae6cb5ff9702f35e216286a73d3de76412b3f42ba42c586` | `fa1d029e150422b8cbf5d444f7ae8dab233c1623f7361ddd17db224742e145a9` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@4d7d2198ea127d986dae18017258e1147269711c19a2eb07a6344b25ccf8bc69` | [`normalization/orientation-deskew/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/orientation-deskew/canonical-build-evidence.json) |
| `hth-perspective-assessment` | `authoritative` | `EXECUTED` | `79` | `38a885be849fb99bba57a2c60e7d345082c46a2a401b459d056f94722331545a` | `46234446ad7cacdabb8da3cf7564c2a4edac94d43d7e088ea3e93930850897a0` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@4d7d2198ea127d986dae18017258e1147269711c19a2eb07a6344b25ccf8bc69` | [`normalization/perspective/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/perspective/canonical-build-evidence.json) |
| `hth-photometric-assessment` | `authoritative` | `EXECUTED` | `79` | `66e7a8e02700bcb56fb9035191e597697acbc8acc22be7a0b8315db7035d887f` | `8e35bb36d3babef7291eccb027842437cee77260253cb5cdb51c8109e6a0523a` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@4d7d2198ea127d986dae18017258e1147269711c19a2eb07a6344b25ccf8bc69` | [`normalization/photometric/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/photometric/canonical-build-evidence.json) |
| `hth-photometric-method-assessment` | `authoritative` | `EXECUTED` | `8` | `658597cc6fe21fcaddb8e9a50d71bca44aeecd667ede0ed415c8f10f64edc0f3` | `291089e8f3ba1ef134b5b8dd4c08edf2e39258c3e19f328b01568e5a68a00125` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@62bf9dd8c1a5f1835a961b7bcfb9d327b2bddcde1869740c01d2be8722b52dee` | [`normalization/photometric-methods/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/photometric-methods/canonical-build-evidence.json) |
| `hth-photometric-validation` | `authoritative` | `EXECUTED` | `921` | `60a76a537aabe8efd15a67fa3ab85f1d7214b7d330ab36938ae5b09e1f285c96` | `f5afb0a51d5b9b856805a9b1dd36d1c692a50d3be87fa11225117ae7d5bfac12` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@32f43540f1bf54e318963ab6c4af0aec7923272505a1c0e6d23def7c2a56734b` | [`normalization/photometric-validation/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/normalization/photometric-validation/canonical-build-evidence.json) |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="cache-and-release-lifecycle"></a>
<details open>
<summary><h2>Cache and release lifecycle</h2></summary>

- Resource state identity: [`7e02535c1537c3d2d451e6cdf134b6bd12a4f8f58429c392e66c1ad26ab50602`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/2d856b021964f6ebb5ca5d2c5a28505ec93f7a9b/metadata/resource-lifecycle.json)
- Build records: `140`
- Cache elements: `140` total; `111` dirty; `0` cleanup-eligible
- Release elements: `55` total; `42` dirty; `3` cleanup-eligible
- Cleanup action: `none` — this is a provenance and eligibility report, not a deletion job.

[↑ Back to Navigation](#table-of-contents)

<a id="cleanup-eligible-releases-3"></a>
<details>
<summary><h3>Cleanup-eligible releases (3)</h3></summary>

| Release | Kind | Integrity | Lineage | Publication | Reason |
|---|---|---|---|---|---|
| `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-BINARIZATION-b1881012e53c85ff792a9c65ac2cd9cdfa8c7e74e3566c730e087a58a626aca4` | `regular` | `unknown` | `superseded` | `latest` | `superseded-unreferenced-inventory-release` |
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

- [Normalization design, provenance, policy, and operating guidance](https://github.com/dlstupka/hth/blob/54b74f11067c52d466f74d34c4e31ce7a102deb1/docs/normalization.md)

</details>

[↑ Back to Navigation](#table-of-contents)
