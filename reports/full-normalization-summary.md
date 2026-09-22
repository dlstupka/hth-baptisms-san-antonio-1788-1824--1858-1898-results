# Full normalization summary

<a id="table-of-contents"></a>

<details open>
<summary><strong>Navigation</strong></summary>

- [Audit status](#audit-status)
- [Normalization result chain](#normalization-result-chain)
- [Canonical Build Evidence ledger](#canonical-build-evidence-ledger)
- [Cache and release lifecycle](#cache-and-release-lifecycle)
- [Engineering recommendations](#engineering-recommendations)
- [Engineering reference](#engineering-reference)

</details>


> Audit report generated exclusively from persisted Canonical Build Evidence, normalization manifests, and the resource-lifecycle ledger. No normalization pixels or domain results were recomputed.

<a id="audit-status"></a>
<details open>
<summary><h2>Audit status</h2></summary>

- Status: **INCOMPLETE**
- Authoritative normalization CBE stages: `28/28`
- Durable transformation manifests: `7/7` valid
- Resource lifecycle ledger: `missing`
- Results snapshot: [`c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/commit/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d)
- Report Writer run: [workflow run](https://github.com/dlstupka/hth/actions/runs/35793589981)

> **Incomplete evidence:** this report identifies absent durable inputs rather than inferring or rebuilding them.

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="normalization-result-chain"></a>
<details open>
<summary><h2>Normalization result chain</h2></summary>

| Stage | Status | Method / policy | Pages | Corrected | Preserved | Result identity |
|---|---:|---|---:|---:|---:|---|
| Canonical crop/orientation | `complete` | `axis-aligned-detector-envelope-v1+hough-lines-conservative-v1` | `929` | `12` | `917` | [`d0fb2998d1cfcef91f6c6469ff9223184243aedebb85bf1746ab13b8c1d26e80`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/normalization-manifest.json) |
| Photometric | `complete` | `background-division-50` | `929` | `87` | `842` | [`7b07faf833091821cd98cf614b113dcc23aaf7b98298fc1a5c06105ccbb5a109`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/photometric-integration/photometric-normalization-manifest.json) |
| Tonal | `complete` | `none` | `929` | `0` | `929` | [`ee25322d85649442f0346f75fbe4c4944925a4eaa23bf1d64838e158d1dba13d`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/tonal-integration/tonal-normalization-manifest.json) |
| Chromatic | `complete` | `none` | `929` | `0` | `929` | [`24606577b231c1140751648b6b751d454d57835d4c74d1dbdb833e43f64d9a8c`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/chromatic-integration/chromatic-normalization-manifest.json) |
| Denoising | `complete` | `none` | `929` | `0` | `929` | [`cb8d44356a75cb14eab58782cc33258773ff3a3ff4e0767eea55ea93f82fd587`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/denoising-integration/denoising-normalization-manifest.json) |
| Sharpening | `complete` | `none` | `929` | `0` | `929` | [`f2c905dca167dab495a86eb873dc078bbe1dc8a0431d26365510ec290e8ddea5`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/sharpening-integration/sharpening-normalization-manifest.json) |
| Binarization | `complete` | `none` | `929` | `0` | `929` | [`46d335fccbc91a8b268f118a4b83424617612ee648d899138c5c840d58056866`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/binarization-integration/binarization-normalization-manifest.json) |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="canonical-build-evidence-ledger"></a>
<details>
<summary><h2>Canonical Build Evidence ledger</h2></summary>

| Stage scope | State | Activity | Pages | Effective build | Canonical result | Source release utilized | Evidence |
|---|---:|---|---:|---|---|---|---|
| `hth-normalization` | `authoritative` | `EXECUTED` | `929` | `2e8ab1f37673af88d32aac59897010d1cf3689682b924778f3bf287a0ad805e1` | `47e57a1cab3771c14d092bfd3f54ddd5a2bf926b5ecce4fd1f7e2df9332aefcf` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@01a148471774734ca79bc0ac092cad7e61fbfbc171b5cc58e6339ad3b499dd3b` | [`normalization/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/canonical-build-evidence.json) |
| `hth-photometric-integration` | `authoritative` | `EXECUTED` | `929` | `0b58045bc95692c2beb82b0ba22c8cefe6b83087638d5b8e93e11893aa0b3403` | `4091c531289c856862a73cfdb86c2074ab9ce691808715c86d8fcdcf4d36ab7f` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@a485dd92959c6290e792214fcbd062b79132e668678fccd980b7d0a15e04d2ab` | [`normalization/photometric-integration/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/photometric-integration/canonical-build-evidence.json) |
| `hth-tonal-assessment` | `authoritative` | `EXECUTED` | `929` | `193ab464c144f91c9793fdc4ec939bd4aa477f4183807bfe33dc2cb9b7e32a19` | `b70efef9ca06774529d5127fb6109a3b071e5574ab4bad865cc7ee19c80a748d` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-PHOTOMETRIC-7b07faf833091821cd98cf614b113dcc23aaf7b98298fc1a5c06105ccbb5a109` | [`normalization/tonal/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/tonal/canonical-build-evidence.json) |
| `hth-tonal-method-assessment` | `authoritative` | `EXECUTED` | `138` | `f42b9351c003d891194deb42b0099e9eb06ece6d7ec0c8c59fb301c0255cd334` | `165ccf9e38a1aaec533c8e1b16590fa4a18c53b0ba129dbc41c25a0e8ab82d46` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-PHOTOMETRIC-7b07faf833091821cd98cf614b113dcc23aaf7b98298fc1a5c06105ccbb5a109` | [`normalization/tonal-methods/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/tonal-methods/canonical-build-evidence.json) |
| `hth-tonal-validation` | `authoritative` | `EXECUTED` | `535` | `572ead4c01fc869cf414f6a20ba2d00f587b4e36c4270fe170602dafb05338eb` | `2fa401b3386734198a25824883fec617f1625ca7a9d67e7ea3c96bc5c0e15bdd` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-PHOTOMETRIC-7b07faf833091821cd98cf614b113dcc23aaf7b98298fc1a5c06105ccbb5a109` | [`normalization/tonal-validation/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/tonal-validation/canonical-build-evidence.json) |
| `hth-tonal-integration` | `authoritative` | `EXECUTED` | `929` | `e3ff423c5b82723335018c2c556f9b64d83da7e96e4400a6243e7cd050109075` | `b32672a2a8eb02c5a82a297f8c45bc47aaa72606d2c85f901ebd0a8582fea646` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-PHOTOMETRIC-7b07faf833091821cd98cf614b113dcc23aaf7b98298fc1a5c06105ccbb5a109` | [`normalization/tonal-integration/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/tonal-integration/canonical-build-evidence.json) |
| `hth-chromatic-assessment` | `authoritative` | `EXECUTED` | `929` | `fbea79dc7cf1a55542166f46ee32446bb953e694e6740f1cfd7c3ee496be442c` | `9b5d3e646c6ba14885d7d8f629f1a323923db70dd8d505188eaa517ddb6fcfe1` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-TONAL-ee25322d85649442f0346f75fbe4c4944925a4eaa23bf1d64838e158d1dba13d` | [`normalization/chromatic/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/chromatic/canonical-build-evidence.json) |
| `hth-chromatic-method-assessment` | `authoritative` | `EXECUTED` | `0` | `909b4f79d4af81c94da0ff8e4833b87ead5d1d88705166eb5ae2e80336a5a804` | `1b6787121996d643819eddd28a747f945ea6207962bec345668f2323cac33c60` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-TONAL-ee25322d85649442f0346f75fbe4c4944925a4eaa23bf1d64838e158d1dba13d` | [`normalization/chromatic-methods/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/chromatic-methods/canonical-build-evidence.json) |
| `hth-chromatic-validation` | `authoritative` | `EXECUTED` | `0` | `fff04bcd05154493dff074da34cc3781f569ec32a5d0fd5a325d61e6baadaf88` | `42e0cde53872f5e5cded945e4c53c105be737b9456a857cd6e0101032ce1c0f3` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-TONAL-ee25322d85649442f0346f75fbe4c4944925a4eaa23bf1d64838e158d1dba13d` | [`normalization/chromatic-validation/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/chromatic-validation/canonical-build-evidence.json) |
| `hth-chromatic-integration` | `authoritative` | `EXECUTED` | `929` | `910b130946808b915d719e26cbecdf3c8c72ebf12daa70f386f35f89b046fc7c` | `a65a9003cf6ff9d59f27360bd37dc2758cfbc2413fe63fede2c44e3ef80681ba` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-TONAL-ee25322d85649442f0346f75fbe4c4944925a4eaa23bf1d64838e158d1dba13d` | [`normalization/chromatic-integration/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/chromatic-integration/canonical-build-evidence.json) |
| `hth-denoising-assessment` | `authoritative` | `EXECUTED` | `929` | `6d95d48341c9671c4cb9d084fc95ace3bbef93e78caa2727a39596028c75d1f2` | `91c32c85bbdcddd4378ce13a9a0bbef4aa72c46f543d6e8de33e24198b1cf235` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-CHROMATIC-24606577b231c1140751648b6b751d454d57835d4c74d1dbdb833e43f64d9a8c` | [`normalization/denoising/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/denoising/canonical-build-evidence.json) |
| `hth-denoising-method-assessment` | `authoritative` | `EXECUTED` | `185` | `9affb36dc4f401d9adfbb76c4d387fc353de2248d168dcb60d98a7b688c96997` | `83889895bb9308fd8c5b04fa74746c3bb92da82344716a47d052ead28381f2aa` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-CHROMATIC-24606577b231c1140751648b6b751d454d57835d4c74d1dbdb833e43f64d9a8c` | [`normalization/denoising-methods/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/denoising-methods/canonical-build-evidence.json) |
| `hth-denoising-validation` | `authoritative` | `EXECUTED` | `742` | `fb8255083c0644dc4b1bdf752a13982ac8c94acab9e2e6eb7121824fc4adebf5` | `652cd09d303eec29d243e1dcf549f933b2d60224aa0b2d498104c7f59bcd0f03` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-CHROMATIC-24606577b231c1140751648b6b751d454d57835d4c74d1dbdb833e43f64d9a8c` | [`normalization/denoising-validation/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/denoising-validation/canonical-build-evidence.json) |
| `hth-denoising-integration` | `authoritative` | `EXECUTED` | `929` | `721b82664886bdb3c8e33988e55ff6f45dd1b4a7a1fe2b4aa09cddbe11f1b79a` | `dababfb26cf8d17b65b6902b9deba9b7d89ed3c7cd58e4350ac6b9094c6f849c` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-CHROMATIC-24606577b231c1140751648b6b751d454d57835d4c74d1dbdb833e43f64d9a8c` | [`normalization/denoising-integration/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/denoising-integration/canonical-build-evidence.json) |
| `hth-sharpening-assessment` | `authoritative` | `EXECUTED` | `929` | `2f296082d742f87e8d05087615ccbeda60dcb2b5d7e4f3a1afcf1387bca4f02c` | `2fe48dd56537c50f7214cb83ff76a4a84bdf2450e59d7a688b70397320ee5ded` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-DENOISING-cb8d44356a75cb14eab58782cc33258773ff3a3ff4e0767eea55ea93f82fd587` | [`normalization/sharpening/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/sharpening/canonical-build-evidence.json) |
| `hth-sharpening-method-assessment` | `authoritative` | `EXECUTED` | `1` | `982b999e21cae6a1b17f709f8e747f6c760753539c1976751937ac826be1adb3` | `9bb6bb8efc833d527274f13e31180173b58f20e7a959e2ed261f573fee46dbe4` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-DENOISING-cb8d44356a75cb14eab58782cc33258773ff3a3ff4e0767eea55ea93f82fd587` | [`normalization/sharpening-methods/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/sharpening-methods/canonical-build-evidence.json) |
| `hth-sharpening-validation` | `authoritative` | `EXECUTED` | `1` | `b680f800ee194f8824613a474138f32ed8be1a876c463ad276476b02ab8476cf` | `957e2c0a7a40985189dc473470e6842a87c54b6c1fb2d0f23e8648c8769e3edf` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-DENOISING-cb8d44356a75cb14eab58782cc33258773ff3a3ff4e0767eea55ea93f82fd587` | [`normalization/sharpening-validation/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/sharpening-validation/canonical-build-evidence.json) |
| `hth-sharpening-integration` | `authoritative` | `EXECUTED` | `929` | `5e081d4cd8d45a839663089f7b33d3396b32835a80cd3327d2bea58eb745096d` | `094bb23bcf12fac8754f327a0cf630ccdf8f467feacf8e2e97621d3c5bd232ad` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-DENOISING-cb8d44356a75cb14eab58782cc33258773ff3a3ff4e0767eea55ea93f82fd587` | [`normalization/sharpening-integration/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/sharpening-integration/canonical-build-evidence.json) |
| `hth-binarization-assessment` | `authoritative` | `EXECUTED` | `929` | `255ccd1842669dee3e9211f3e516e21010485da96a9a19ea71efb7eabc33a282` | `fa91013879d312474a5fce31dac72a460540eb6c6931d59971f56c5855713f2a` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-SHARPENING-f2c905dca167dab495a86eb873dc078bbe1dc8a0431d26365510ec290e8ddea5` | [`normalization/binarization/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/binarization/canonical-build-evidence.json) |
| `hth-binarization-method-assessment` | `authoritative` | `EXECUTED` | `185` | `863f8eb6eeae6fe3339ef6e7f491af63122b032c33bd250ca2a226084e58cddb` | `f40c9d371e96eb707ba9b7f0086902ce6cfcb636f140ebb8300c563f0687586d` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-SHARPENING-f2c905dca167dab495a86eb873dc078bbe1dc8a0431d26365510ec290e8ddea5` | [`normalization/binarization-methods/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/binarization-methods/canonical-build-evidence.json) |
| `hth-binarization-validation` | `authoritative` | `EXECUTED` | `738` | `67d787abcbebb7a0e5b16c60a35466ab48082db01d0d029ae94feb3747899935` | `451ccd43b668627d73e3d8536c911639ec8434c1feb3a6411c8ad914b778fb00` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-SHARPENING-f2c905dca167dab495a86eb873dc078bbe1dc8a0431d26365510ec290e8ddea5` | [`normalization/binarization-validation/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/binarization-validation/canonical-build-evidence.json) |
| `hth-binarization-integration` | `authoritative` | `EXECUTED` | `929` | `162c676313ffbbda2e540e5662eb7f85c6ad96f95d693303bf5225e067b50426` | `80540118682b293409cfbf0b10e24b06ec666164a9b296a7d065fcca7e77b3c5` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@HTH-SHARPENING-f2c905dca167dab495a86eb873dc078bbe1dc8a0431d26365510ec290e8ddea5` | [`normalization/binarization-integration/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/binarization-integration/canonical-build-evidence.json) |
| `hth-crop-framing-assessment` | `authoritative` | `EXECUTED` | `18` | `bc9a8602808c9e2efbd2ec0bfc0938cd1fa8a021bba4df93b7865056db3f3d0e` | `9d011c44b4bbb517f7b2ee4a53a73baec2c1ec147b7512b96605b5fc5e3dbbab` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898@HTH-GOLDEN-0002` | [`normalization/crop-framing/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/crop-framing/canonical-build-evidence.json) |
| `hth-orientation-deskew-assessment` | `authoritative` | `EXECUTED` | `79` | `fbfdc69bf1d741790a7ca3d284d923573a21189daa59897f892d58fc589a4cd7` | `54f5cfb5ba4faf8dbe714f30fd377358d95e1811c7d5b4a1135845f0c0934b54` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@2e8ab1f37673af88d32aac59897010d1cf3689682b924778f3bf287a0ad805e1` | [`normalization/orientation-deskew/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/orientation-deskew/canonical-build-evidence.json) |
| `hth-perspective-assessment` | `authoritative` | `EXECUTED` | `79` | `8d794ef867bb891469fc4b32c4ddc43a17ac9e17c2adaf673c6bfe5aa0bfd142` | `55515ccb361f1bc22aea5f2601a53f9cba68a6ea3f2c0a0a17a6c6a613a83884` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@2e8ab1f37673af88d32aac59897010d1cf3689682b924778f3bf287a0ad805e1` | [`normalization/perspective/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/perspective/canonical-build-evidence.json) |
| `hth-photometric-assessment` | `authoritative` | `EXECUTED` | `79` | `3193b5abfb3e4da71702d4822fb82aa450fce272d9f8d0d458168bba8d15e2f7` | `20142e81d22522539aa79e89161d0b36a9acb436717fd72b0de7a786af2bccb4` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@2e8ab1f37673af88d32aac59897010d1cf3689682b924778f3bf287a0ad805e1` | [`normalization/photometric/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/photometric/canonical-build-evidence.json) |
| `hth-photometric-method-assessment` | `authoritative` | `EXECUTED` | `8` | `1c41d4b2d5a86bb988ab1029520444f1fc2487315cb5c9bcee6b9ab13ad2f84f` | `291089e8f3ba1ef134b5b8dd4c08edf2e39258c3e19f328b01568e5a68a00125` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@62bf9dd8c1a5f1835a961b7bcfb9d327b2bddcde1869740c01d2be8722b52dee` | [`normalization/photometric-methods/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/photometric-methods/canonical-build-evidence.json) |
| `hth-photometric-validation` | `authoritative` | `EXECUTED` | `921` | `e18f98a650b8282ca4922eee21b7428036e38cb877acdd8eb2e55928c3eeac7f` | `f5afb0a51d5b9b856805a9b1dd36d1c692a50d3be87fa11225117ae7d5bfac12` | `dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results@32f43540f1bf54e318963ab6c4af0aec7923272505a1c0e6d23def7c2a56734b` | [`normalization/photometric-validation/canonical-build-evidence.json`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/normalization/photometric-validation/canonical-build-evidence.json) |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="cache-and-release-lifecycle"></a>
<details open>
<summary><h2>Cache and release lifecycle</h2></summary>

- Ledger: [`missing`](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/c9f9e0ff9a92f89b49ce6de08297e81e7ab6285d/metadata/resource-lifecycle.json)

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="engineering-recommendations"></a>
<details open>
<summary><h2>Engineering recommendations</h2></summary>

- Restore or regenerate only the missing durable evidence identified above, then rerun Report Writer; do not infer completion from workflow success alone.

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="engineering-reference"></a>
<details>
<summary><h2>Engineering reference</h2></summary>

- [Normalization design, provenance, policy, and operating guidance](https://github.com/dlstupka/hth/blob/d798b1a03d939bdf2ff4b4570f6b60e6612409ec/docs/normalization.md)

</details>

[↑ Back to Navigation](#table-of-contents)
