# Changelog

## 1.0.0 (2025-08-30)

### ⚠ BREAKING CHANGES

* **map:** `map.jinja` now exports a generic `mapdata` variable
* **map:** The per grain parameter values are now under `TEMPLATE/parameters/`
* changed all state names and ids
* **pkgname:** the parameter `pkg` is now a dictionary. References
 to `template.pkg` should be changed to `template.pkg.name`.
* **tofs:** every formula writer will need to change the import
to use this new version.

* template/libtofs.jinja: provides the “files_switch” macro.

* docs/TOFS_pattern.rst: update documentation to use the new path.

* template/config/clean.sls: change import from “macros.jinja” to “libtofs.jinja”.

* template/config/file.sls: ditoo.
* **states:** Wholesale state ID changes will break implementations
that are relying on the previous state IDs for requisite purposes.
* **pkg:** Changing the `pkg` directory to `package` will break
implementations that are depending on `pkg` for `include` or `sls`-based
requisite purposes.

### Features

* add Gentoo support ([4c2f4ed](https://github.com/dafyddj/tmp-test-template-formula/commit/4c2f4ede0223e83e1958be33288fa6b83cce7140))
* add script to ease conversion from template to real formula ([edfa269](https://github.com/dafyddj/tmp-test-template-formula/commit/edfa269e9655407ca26788a8d5564c759abbbb30))
* **authors:** update automatically alongside `semantic-release` ([8000098](https://github.com/dafyddj/tmp-test-template-formula/commit/80000982e2e94df1bf6c23f913b6fe3f34e8e23a))
* **centos-6:** reshape formula and tests for this platform ([a4b1608](https://github.com/dafyddj/tmp-test-template-formula/commit/a4b1608ab4c227cf9fe6ceed1e2bae20a42c92cf)), closes [#104](https://github.com/dafyddj/tmp-test-template-formula/issues/104)
* **convert-formula.sh:** assign `@NONE` as whole-formula owner ([cceffff](https://github.com/dafyddj/tmp-test-template-formula/commit/cceffffef5924b6c156890562e6f64f4872d6867))
* **kitchen+travis:** add `opensuse-leap` after resolving issues ([7614a3c](https://github.com/dafyddj/tmp-test-template-formula/commit/7614a3cd7d199969496025aa0129bb6e142af7a4))
* **kitchen+travis:** conduct tests on a wider range of platforms ([1348078](https://github.com/dafyddj/tmp-test-template-formula/commit/1348078395dbff459a37a7cccc9d0eeb99562574))
* **m2r:** use `m2r` to convert automatic `.md` files to `.rst` ([b86ddf4](https://github.com/dafyddj/tmp-test-template-formula/commit/b86ddf4ce70c82e24860298ef33bddc91cf2f422))
* **macos:** basic package and group handling ([8c3fe22](https://github.com/dafyddj/tmp-test-template-formula/commit/8c3fe22822c5bef5cad29b0e813c91507253050a))
* **map:** generate a YAML file to validate `map.jinja` ([fc90075](https://github.com/dafyddj/tmp-test-template-formula/commit/fc90075dd94d874eb283d96259f552812d8a8d82))
* **mapping:** introduce osarchmap per issue [#13](https://github.com/dafyddj/tmp-test-template-formula/issues/13) ([41ac40d](https://github.com/dafyddj/tmp-test-template-formula/commit/41ac40d958fa3744e4908bc25be1cd27b0275e0f))
* **map:** update to v5 `map.jinja` ([42e1932](https://github.com/dafyddj/tmp-test-template-formula/commit/42e19322c9c4d91a6cfa1e406723b5a799f33f80))
* **pkg:** add `clean` states ([422c7ac](https://github.com/dafyddj/tmp-test-template-formula/commit/422c7ac212e4bb0f01a8ce0f0482bf6d92a34438))
* **pkg:** use `require` requisite between `pkg` states ([6e7141b](https://github.com/dafyddj/tmp-test-template-formula/commit/6e7141babf2eaf8bfbbe089675f50420ccebe7c7))
* **rtd:** provide custom CSS file for overriding in-use Sphinx theme ([24bd338](https://github.com/dafyddj/tmp-test-template-formula/commit/24bd3383346a907b0e08ef4ec17b53ad232e0a0e))
* **semantic-release:** configure for this formula ([cbcfd75](https://github.com/dafyddj/tmp-test-template-formula/commit/cbcfd75b31f1df9a9f4cdaf931d070dc59b2f1c6))
* **sub-component:** manage a dedicated configuration file ([c4440d7](https://github.com/dafyddj/tmp-test-template-formula/commit/c4440d7c55480e10c2330d0a7d760a22f71b805b))
* **toc:** use `markdown-toc` directly to update inline ([a5bae1e](https://github.com/dafyddj/tmp-test-template-formula/commit/a5bae1efe0066881e153cc060c1198e1c76d0eed))
* **tofs:** implement backwards-compatible TOFSv2 for configurability ([068a94d](https://github.com/dafyddj/tmp-test-template-formula/commit/068a94d3a242ec818640205626b011f8e53acf1a))
* **tofs:** lookup files directory in “tpldir” hierarchy ([5c495fb](https://github.com/dafyddj/tmp-test-template-formula/commit/5c495fb63a128527baf58745b5e0ce981b331f69))
* **workflows:** dry-run `semantic-release` in GitHub Actions ([764cd4c](https://github.com/dafyddj/tmp-test-template-formula/commit/764cd4ca8a735b4995162c4be8fea57e3dabba81))
* **yamllint:** include for this repo and apply rules throughout ([e76525f](https://github.com/dafyddj/tmp-test-template-formula/commit/e76525f130650308b2f9bd859b0e57f8e230b8fc))

### Bug Fixes

* **_mapdata:** ensure map data is directly under `values` ([bcb8e29](https://github.com/dafyddj/tmp-test-template-formula/commit/bcb8e29b687f9804a1cfbda1253da290432cd5b0))
* **`config/file`:** add missing space before Jinja `}}` ([5cd08ab](https://github.com/dafyddj/tmp-test-template-formula/commit/5cd08abef2e2b2669fe0c3df706971608fe48721))
* **`libtofs`:** use `select` to deal with empty strings in path ([afe0751](https://github.com/dafyddj/tmp-test-template-formula/commit/afe075141f561d0b1e1edf2d2f27dcb2c9cabc7e))
* **`libtofs`:** use `strip` to deal with leading/trailing slashes ([2563a46](https://github.com/dafyddj/tmp-test-template-formula/commit/2563a46d5be9cea69cd0e9cc6f627b82d70f9d45))
* **`map.jinja`:** _merge_ defaults and `config.get` ([91bc2f0](https://github.com/dafyddj/tmp-test-template-formula/commit/91bc2f046b3629b9f1f66ed0eacddb626348da6c))
* **`map.jinja`:** remove `merge` from `config.get` (for `salt-ssh`) ([00e474c](https://github.com/dafyddj/tmp-test-template-formula/commit/00e474cdc25c0bc8502826336138cdec9d0c71f5)), closes [#95](https://github.com/dafyddj/tmp-test-template-formula/issues/95)
* **`map.jinja`:** use tplroot ([b9c5e03](https://github.com/dafyddj/tmp-test-template-formula/commit/b9c5e030bc5fe4f903f5fbd994966331523fc405))
* broken install-hooks due to saltlint v0.8.0 ([7da11c9](https://github.com/dafyddj/tmp-test-template-formula/commit/7da11c9c3ace8efc379cdec804420ca810e43548))
* **codeowners:** ensure `lib*` files are owned by `ssf` ([d60cc15](https://github.com/dafyddj/tmp-test-template-formula/commit/d60cc1536637831ef76b2f2c84086b3f88f2684f))
* **comments:** explain that at least an empty dict is required ([426f955](https://github.com/dafyddj/tmp-test-template-formula/commit/426f955a791053c7eae1cd3b3fe5c87f84689181)), closes [#93](https://github.com/dafyddj/tmp-test-template-formula/issues/93)
* **commitlint:** fix header length at 72 chars as agreed ([a95061d](https://github.com/dafyddj/tmp-test-template-formula/commit/a95061ddd088210c5111490234bc1588002cddd5))
* **convert-formula.sh:** add -_ to allowed chars in formula name ([a999fee](https://github.com/dafyddj/tmp-test-template-formula/commit/a999fee2145d9b0484049808c3c331943580cc3f))
* **convert-formula.sh:** add `~` to reST underlining during conversion ([80ed8cd](https://github.com/dafyddj/tmp-test-template-formula/commit/80ed8cd4153f99ec0acaac2996387f565981e7aa))
* **convert-formula.sh:** apply remaining suggestions from [#180](https://github.com/dafyddj/tmp-test-template-formula/issues/180) ([76ecd44](https://github.com/dafyddj/tmp-test-template-formula/commit/76ecd447be66fd9b33ace56836796d3ce24537db))
* **convert-formula.sh:** delete all existing tags ([7c33601](https://github.com/dafyddj/tmp-test-template-formula/commit/7c33601fd455df90b1082791cdd282a507334898)), closes [#210](https://github.com/dafyddj/tmp-test-template-formula/issues/210)
* **convert-formula.sh:** fix reST underlining during conversion ([11068af](https://github.com/dafyddj/tmp-test-template-formula/commit/11068afae9a3b6957695b79f92b4588388a13632))
* **convert-formula.sh:** remove "Using this template" post-conversion ([55ab937](https://github.com/dafyddj/tmp-test-template-formula/commit/55ab937c047374fce0548d8c18e8513bc15ead78))
* **convert-formula.sh:** remove `rubocop` override post-conversion ([aca4e44](https://github.com/dafyddj/tmp-test-template-formula/commit/aca4e4428964da745e7b1b7dce15d2c751f76490))
* **convert-formula.sh:** remove CI test post-conversion ([06ec949](https://github.com/dafyddj/tmp-test-template-formula/commit/06ec949fd17bb4b52bb230a6ad2eddfe08a4e693))
* **convert-formula.sh:** replace instances of `template-formula` for CI ([537fe65](https://github.com/dafyddj/tmp-test-template-formula/commit/537fe65d456741e64823af33865f34457e0e3853)), closes [#231](https://github.com/dafyddj/tmp-test-template-formula/issues/231)
* **convert-formula.sh:** reset version to `1.0.0` ([39889ce](https://github.com/dafyddj/tmp-test-template-formula/commit/39889ce303cb57125ba0411ab55266ee018d40e1))
* **convert-formula.sh:** use portable sed function to make replacements ([41e10b5](https://github.com/dafyddj/tmp-test-template-formula/commit/41e10b5249e0c8827844f438d1995cf7cb42d63a)), closes [#192](https://github.com/dafyddj/tmp-test-template-formula/issues/192)
* **convert-formula:** `_mapdata` control name must use the formula one ([1f3600d](https://github.com/dafyddj/tmp-test-template-formula/commit/1f3600d66fd710bd1a41cb937cb345369d0e3e18))
* fix `CentOS Linux-7` and add `os` details from current CI setup ([4be16ca](https://github.com/dafyddj/tmp-test-template-formula/commit/4be16ca4befeddeeb8be1199cd088df7c547523f))
* **formula:** update to current oldest supported version of Salt ([878eca1](https://github.com/dafyddj/tmp-test-template-formula/commit/878eca189b79dfb35fe7c95ea95cf532644edc68))
* get a release out ([53cbbde](https://github.com/dafyddj/tmp-test-template-formula/commit/53cbbde332da48e8e16d8a88b11a3e07db0793ec))
* **gitignore:** add Gemfile.lock to .gitignore ([87fa410](https://github.com/dafyddj/tmp-test-template-formula/commit/87fa4100a5e27bb11242c50338f1d7cb26713eef))
* **grain:** fix grain value ([26edfa0](https://github.com/dafyddj/tmp-test-template-formula/commit/26edfa08c6bc2791eb8375a1db70b9f76ff4e3a2))
* **inspec:** validate `map.jinja` configuration ([41d222e](https://github.com/dafyddj/tmp-test-template-formula/commit/41d222e30c0da10fabeea23a7ab2886f02ea6479))
* **libmapstack:** allow mapping by booleans and numbers ([bb3a7ea](https://github.com/dafyddj/tmp-test-template-formula/commit/bb3a7ea0b208eeb2b6472ca9cb011935032c0356))
* **libsaltcli+libmatchers:** ensure Salt client API detection [skip ci] ([6eb2073](https://github.com/dafyddj/tmp-test-template-formula/commit/6eb2073d02ff8006dac86c59e683ae983ecccd25))
* **libsaltcli:** update `salt-ssh` detection for `enable_ssh_minions` ([f0e7192](https://github.com/dafyddj/tmp-test-template-formula/commit/f0e7192fb5a546cb0569f9d4257807c8592a00b6))
* **libtofs:** “files_switch” mess up the variable defined by “map.jinja” ([ab4ce75](https://github.com/dafyddj/tmp-test-template-formula/commit/ab4ce751a4640303af7acbf7a278aef79b530bb6))
* **libtofs:** “files_switch” mess up the variable exported by “map.jinja” [skip ci] ([241646f](https://github.com/dafyddj/tmp-test-template-formula/commit/241646fe96447369df00f17ec1c27a53de08bec4))
* **libtofs:** avoid using subpath by default ([c07471d](https://github.com/dafyddj/tmp-test-template-formula/commit/c07471da124a6445bf0fd0377606b9a937109e79))
* **libtofs:** don't crash if “tofs.files_switch” lookup a list ([0979d35](https://github.com/dafyddj/tmp-test-template-formula/commit/0979d359fd1da219b32e4d2f8937336f2f061784))
* **pillar:** fix `os_family` typo ([3f89c12](https://github.com/dafyddj/tmp-test-template-formula/commit/3f89c1224896453f541f7334c0258130d12bb787))
* **release.config.js:** use full commit hash in commit link [skip ci] ([4ac8d92](https://github.com/dafyddj/tmp-test-template-formula/commit/4ac8d92778977ed63fe99e4506a2b0a2d41a2bce))
* **rubocop:** add fixes using `rubocop --safe-auto-correct` ([484ce24](https://github.com/dafyddj/tmp-test-template-formula/commit/484ce2459dd0a598954fc0ee2656685f134f757d))
* **rubocop:** fix remaining errors manually ([9566b6f](https://github.com/dafyddj/tmp-test-template-formula/commit/9566b6fb6317132345a9a2f2320201d2f30128ac))
* **running.sls:** use `watch` not `require` to ensure service restart ([3a1fc35](https://github.com/dafyddj/tmp-test-template-formula/commit/3a1fc35a13f66714cd42583f13679c6f189ae48f))
* **subcomponent:** clean referencing wrong sls ([394808e](https://github.com/dafyddj/tmp-test-template-formula/commit/394808ebda03a8981af131061bdfd99a296a83c4))
* **suse:** correct OS grain ([6aee580](https://github.com/dafyddj/tmp-test-template-formula/commit/6aee5804d3d4282322c6421befefa7b803eca699))
* **tofs:** prepend the config-based `source_files` to the default ([3483e76](https://github.com/dafyddj/tmp-test-template-formula/commit/3483e760bff6bef763aedaf9e4c7bcec8aa6bfc1)), closes [#151](https://github.com/dafyddj/tmp-test-template-formula/issues/151)
* **tofs:** update comments in `files_switch` macro for new method ([3fa3640](https://github.com/dafyddj/tmp-test-template-formula/commit/3fa36402b79daf56e85def96dc4170f8f99c8596))
* **tofs:** update use of state ID in `config` and `pillar` ([3d9a24c](https://github.com/dafyddj/tmp-test-template-formula/commit/3d9a24c71dc2cae3dd33fd07c68660128cd5c4f4))
* **tofs:** use `source_files` instead of `files` ([5110716](https://github.com/dafyddj/tmp-test-template-formula/commit/51107165f07b7de4fa6aa297e7f0546e2c8de598))
* **tofs:** use `tpldir` derivative `topdir` for pillar (config) paths ([5e9df00](https://github.com/dafyddj/tmp-test-template-formula/commit/5e9df004d97fde7adb98550f0dcf8f2807d60b67))
* **travis:** don't install gems twice ([925d8e2](https://github.com/dafyddj/tmp-test-template-formula/commit/925d8e2dc80ba1d69b337bddea13e1611e8761c7))
* **travis:** reinstate conversion test [skip ci] ([5d47fda](https://github.com/dafyddj/tmp-test-template-formula/commit/5d47fda1b9f52bff1a4c2cad5097cd3d8cd43521))
* **travis:** use version numbers in Gemfile to prevent failed builds ([35f7111](https://github.com/dafyddj/tmp-test-template-formula/commit/35f71113cf26e97fd4717ad96f75b63fcd170923))
* typo in the installation instructions ([306a0d9](https://github.com/dafyddj/tmp-test-template-formula/commit/306a0d9b1e209012fb7630d1e1cbfe5ea661a0f6))

### Performance Improvements

* **travis:** improve `salt-lint` invocation [skip ci] ([7a96cd7](https://github.com/dafyddj/tmp-test-template-formula/commit/7a96cd77db71eb8b022df7bd5c1014664124a022))

### Reversions

* **kitchen+travis:** disable `debian-8` due to `2019.2` bug ([e8f0f7e](https://github.com/dafyddj/tmp-test-template-formula/commit/e8f0f7ee2ac20e90382c55e751bc5488b4262204))
* **kitchen+travis:** use `debian:jessie-backports` as `debian-8` ([dcd141a](https://github.com/dafyddj/tmp-test-template-formula/commit/dcd141af749b580659b66e42e41d9c97b7903b36))

### Code Refactoring

* **`osfamilymap`:** avoid *BSD ambiguity with MacOS `rootgroup` ([3338605](https://github.com/dafyddj/tmp-test-template-formula/commit/3338605243cc1be9358230d045d8656873cdb93b))
* **components:** split components into separate subdirs ([d957055](https://github.com/dafyddj/tmp-test-template-formula/commit/d95705563c8c2d31766e9be5f53d9ecd3c9ee0ce))
* **config_clean:** remove unused import from `libtofs.jinja` ([b7cb585](https://github.com/dafyddj/tmp-test-template-formula/commit/b7cb5857c5bf475debe2860d6c4438db86aa27fb))
* improve reusability using an unique keyword TEMPLATE ([2e8ded6](https://github.com/dafyddj/tmp-test-template-formula/commit/2e8ded6565f7bad166323792bf42979aac2980fa))
* **include+require:** use variable for duplicate values ([4443518](https://github.com/dafyddj/tmp-test-template-formula/commit/4443518a6349e37e039266de69666a58d79ba70a))
* **kitchen:** `pillars-from-files` => `pillars_from_files` ([7c954a7](https://github.com/dafyddj/tmp-test-template-formula/commit/7c954a7e471df20b19be9a3324206036d958e3d4))
* **kitchen:** prefer `kitchen.yml` to `.kitchen.yml` ([3860bf9](https://github.com/dafyddj/tmp-test-template-formula/commit/3860bf91bda5cde38b3a4e3d87affd9105a2c0e9))
* **libmatchers:** match default type with docs ([8f847be](https://github.com/dafyddj/tmp-test-template-formula/commit/8f847bebfd4809b9c4acbfc1c20c1738243f9fd7))
* **libsaltcli:** use the `opts` dict throughout [skip ci] ([69b632f](https://github.com/dafyddj/tmp-test-template-formula/commit/69b632fbe613d4f99a48f59f64ec93c3897431c8))
* **libtofs:** remove deprecated `v1_path_prefix` argument ([ad2a965](https://github.com/dafyddj/tmp-test-template-formula/commit/ad2a965a15901f2469f401c6c5e45d6fd7115bea))
* **macros:** use `tplroot` instead of `topdir` to match `tpldata` ([923b459](https://github.com/dafyddj/tmp-test-template-formula/commit/923b459d9bc6be9341b92a5cc034dc13056cd095))
* **map.jinja:** standardise v5 structure [skip ci] ([bf9a9bd](https://github.com/dafyddj/tmp-test-template-formula/commit/bf9a9bd20482b5a5a748933094f58a0f88b41aee))
* **map:** use `config.get` instead of `pillar.get` ([5dc0b86](https://github.com/dafyddj/tmp-test-template-formula/commit/5dc0b86b228296ae8c1a2e4b39de2357693c578c))
* **map:** use top-level `values:` key in `map.jinja` dumps ([f8e8fcb](https://github.com/dafyddj/tmp-test-template-formula/commit/f8e8fcb29e77d1afded74a2c92789ac8807a4768))
* **pkg:** change to `package` instead ([2cd82e5](https://github.com/dafyddj/tmp-test-template-formula/commit/2cd82e5076353d63b74cb8b655cd9799ff4ecd9e))
* **pkg:** move `pkg` related components into separate directory ([c21f82b](https://github.com/dafyddj/tmp-test-template-formula/commit/c21f82b8856c88a0f40cadb8681c51b300f4a8cc))
* **pkgname:** reserve 'pkg' as packaging dict ([c6ae81c](https://github.com/dafyddj/tmp-test-template-formula/commit/c6ae81cc65b293744856309d23f51d085cbe069b))
* **service:** use `systemd-journald` instead of `systemd-udevd` ([a265105](https://github.com/dafyddj/tmp-test-template-formula/commit/a2651058be0d8b09f910aeee2f23703b6cefaa09))
* **shellcheck:** fix violation ([4ee6387](https://github.com/dafyddj/tmp-test-template-formula/commit/4ee6387bf97aeb9c965bd2638ba934208d00874c))
* **states:** set state IDs based on a dependable structure ([6690ee6](https://github.com/dafyddj/tmp-test-template-formula/commit/6690ee6591697389dfe81e280bc8f85ad3ea42c3))
* **string:** remove capitalisation from 'template' string ([7062210](https://github.com/dafyddj/tmp-test-template-formula/commit/706221099da0f8e4fc3e53147f1904419bfe2b0a))
* **tofs:** avoid using “salt['config.get']” for formula writers ([60d43e7](https://github.com/dafyddj/tmp-test-template-formula/commit/60d43e7feedcb0aa0b656d6a100d5e8fbea7c881))
* **tofs:** ensure (v2 > v1 > default) checking for `src_files` ([3e62d7b](https://github.com/dafyddj/tmp-test-template-formula/commit/3e62d7b047197d0a3def6465d15d704b8b800d55))
* **tofs:** make `files_switch` macro fully portable ([a98b777](https://github.com/dafyddj/tmp-test-template-formula/commit/a98b77723a1423365da963e3368e891bec9d2bce))
* **tofs:** move “files_switch” macro to “libtofs.jinja” ([da7e692](https://github.com/dafyddj/tmp-test-template-formula/commit/da7e69283ff72425e0b7746f114a0ed46246d861))
* **tofs:** move subcomponent definition to `defaults.yaml` ([c269673](https://github.com/dafyddj/tmp-test-template-formula/commit/c26967329552790cf6e9efb3e61e8e58d92a657a))
* **tofs:** move subcomponent templates to first `source` match ([70cc92d](https://github.com/dafyddj/tmp-test-template-formula/commit/70cc92d8cf5378829385c3b3f7a70eb39d752523))
* **tofs:** use `config` rather than `pillar` throughout ([5730e94](https://github.com/dafyddj/tmp-test-template-formula/commit/5730e94d46299d7b8c90088dad5e58a7f2ee950c))
* **topdir:** use for `include` and `require` except `init.sls` ([a218e91](https://github.com/dafyddj/tmp-test-template-formula/commit/a218e914bc34b3bc55a0c726d07486e08b4d0d0b))
* **tpldir:** use `topdir` globally in place of `tpldir` ([2838bc9](https://github.com/dafyddj/tmp-test-template-formula/commit/2838bc904125918671ad3e73fe1f50885291bf79))
* **tpldir:** use `tpldir` or derivatives to make formula portable ([52d03d8](https://github.com/dafyddj/tmp-test-template-formula/commit/52d03d895ac60cbcef64ca712881eee56d77c21a)), closes [#22](https://github.com/dafyddj/tmp-test-template-formula/issues/22)
* **tplroot:** use `tplroot` instead of `topdir` to match `tpldata` ([b7356b0](https://github.com/dafyddj/tmp-test-template-formula/commit/b7356b0d413e8b9efca87e0635ae16d00c82567d))
* **travis:** merge `lint` stage into the `test` stage ([d3b93f8](https://github.com/dafyddj/tmp-test-template-formula/commit/d3b93f81b14bc2e83b56aa589739147a269c0c30))

### Documentation

* add basic `pre-commit` usage instructions ([c78c068](https://github.com/dafyddj/tmp-test-template-formula/commit/c78c06876eb4c117b3ab00f9da479e8a4c3f1cf5))
* **bug_report:** add section requesting commit hash / release tag ([faccb6a](https://github.com/dafyddj/tmp-test-template-formula/commit/faccb6a705d06ae684e9bcaefe993251456af8c2))
* **bug_report:** group into sections for better logical ordering ([e9b6c2f](https://github.com/dafyddj/tmp-test-template-formula/commit/e9b6c2f8be5cab72290fa1bbbbcde653ef6aa242))
* **changelog:** add missing entry under `v0.3.2` ([50352b5](https://github.com/dafyddj/tmp-test-template-formula/commit/50352b5cf55ce42623cb5bc5e284635d3f5f6a94))
* **changelog:** merge previous `rst` into new `md` format ([2b4e485](https://github.com/dafyddj/tmp-test-template-formula/commit/2b4e48501593b5fece0179b3d7f0c7f4752c7f90))
* **changelog:** remove erroneous "closes" used by `semantic-release` ([be4571d](https://github.com/dafyddj/tmp-test-template-formula/commit/be4571d352d938451e4a50b8b632e92682ef0efd))
* **components:** update for separation of `pkg`, `config` & `service` ([726fcab](https://github.com/dafyddj/tmp-test-template-formula/commit/726fcabc6d36f25f4d5b1286d09789eede7623fa))
* **contributing:** add `bind-formula` to `semantic-release` formulas ([3da78b0](https://github.com/dafyddj/tmp-test-template-formula/commit/3da78b091f88aee8b575560f25cb90a54017b1db))
* **contributing:** add basic introductory text before the TOC ([45ccaf6](https://github.com/dafyddj/tmp-test-template-formula/commit/45ccaf68bd0eb8f44b11eeab8fdd106f456bede0))
* **contributing:** add commit message formatting instructions ([fb3d173](https://github.com/dafyddj/tmp-test-template-formula/commit/fb3d17324cbef458474e1961d923fcd87d4b24a4))
* **contributing:** add documentation contribution guidelines ([dff0ee8](https://github.com/dafyddj/tmp-test-template-formula/commit/dff0ee8ef85923c5998fa9b707ed3828d1fdc52b))
* **contributing:** add recent `semantic-release` formula ([c2924b0](https://github.com/dafyddj/tmp-test-template-formula/commit/c2924b002f631a7fa1a4eb0ad7fdf15138f9f118))
* **contributing:** add recent `semantic-release` formula ([8d2318c](https://github.com/dafyddj/tmp-test-template-formula/commit/8d2318ceaec5b3cc107d0cbd9f666c7e59e4bfaf))
* **contributing:** add recent `semantic-release` formula ([f9def86](https://github.com/dafyddj/tmp-test-template-formula/commit/f9def8661c44f0549a14d47015665c7c07989274))
* **contributing:** add recent `semantic-release` formula ([ed8c55a](https://github.com/dafyddj/tmp-test-template-formula/commit/ed8c55a22a386c0c5ba2daabc80c1addeba4b294))
* **contributing:** add recent `semantic-release` formula ([c679cb5](https://github.com/dafyddj/tmp-test-template-formula/commit/c679cb595f37a32891c03637ac1763804356daa7))
* **contributing:** add recent `semantic-release` formula ([fc50a9e](https://github.com/dafyddj/tmp-test-template-formula/commit/fc50a9e47ecc908f28f82c415572c8133f5527c2))
* **contributing:** add recent `semantic-release` formula ([7f56237](https://github.com/dafyddj/tmp-test-template-formula/commit/7f56237acbc97d1724094593828a3f5e1d60ee27))
* **contributing:** add recent `semantic-release` formula ([486b393](https://github.com/dafyddj/tmp-test-template-formula/commit/486b393233d46b5010f54bf9ebd7cdc539edf4da))
* **contributing:** add recent `semantic-release` formula [skip ci] ([85118de](https://github.com/dafyddj/tmp-test-template-formula/commit/85118deeb9a33db4ff008b526db88f94dd555e50))
* **contributing:** add recent `semantic-release` formulas ([7f36ae9](https://github.com/dafyddj/tmp-test-template-formula/commit/7f36ae96b3785df93a9666d67f23564439a0dd86))
* **contributing:** add recent `semantic-release` formulas ([57d0b85](https://github.com/dafyddj/tmp-test-template-formula/commit/57d0b8507d500457b4cc24c1754b7ec7dc52fad9))
* **contributing:** add recent `semantic-release` formulas ([22052fc](https://github.com/dafyddj/tmp-test-template-formula/commit/22052fcdeebd8f68d52f2faee70e91f205b70b5d))
* **contributing:** add recent `semantic-release` formulas ([461c7a5](https://github.com/dafyddj/tmp-test-template-formula/commit/461c7a571b1a8bcdda34cb7abaa169466d701991))
* **contributing:** add recent `semantic-release` formulas ([#110](https://github.com/dafyddj/tmp-test-template-formula/issues/110)) ([ab7afd4](https://github.com/dafyddj/tmp-test-template-formula/commit/ab7afd414e38ad410dd063ae8577b0d820a827c0))
* **contributing:** add recent `semantic-release` formulas [skip ci] ([e6fb519](https://github.com/dafyddj/tmp-test-template-formula/commit/e6fb519c669b6ac7afee2d002a5eb3f09d4a2405))
* **contributing:** add template-formula to `semantic-release` formulas ([87e4ebc](https://github.com/dafyddj/tmp-test-template-formula/commit/87e4ebc3ef23122dd74405c3336fdc7b6156388d))
* **contributing:** add TOC to match all other pages ([7b1a2a9](https://github.com/dafyddj/tmp-test-template-formula/commit/7b1a2a9a14be10e28dadc1348ea7ea891e5f9d09))
* **contributing:** add ufw formula to semantic release formulas ([18ff689](https://github.com/dafyddj/tmp-test-template-formula/commit/18ff689caa18615c3cf8189ab110d460c0c9a7c7))
* **contributing:** centre-align version bump columns in table ([a238cae](https://github.com/dafyddj/tmp-test-template-formula/commit/a238cae3bf8cbd08741aa28648969974bafaac05))
* **contributing:** convert to `.rst` and move to `docs` subdir ([474f318](https://github.com/dafyddj/tmp-test-template-formula/commit/474f31865386887cad78cce07cb6cdd515b9bc25))
* **contributing:** create blank template ([3633e8f](https://github.com/dafyddj/tmp-test-template-formula/commit/3633e8faa9282d9d6bf0c057dffaab44a12a89b6))
* **contributing:** fix link to contributing docs ([b6a33d3](https://github.com/dafyddj/tmp-test-template-formula/commit/b6a33d3e61f4948e99c5263c47786de97d1f26d9))
* **contributing:** modify quoted heading to prevent TOC inclusion ([abcb6ef](https://github.com/dafyddj/tmp-test-template-formula/commit/abcb6ef399ec0d1021812015b1a2e38f2a223d26))
* **contributing:** remove to use org-level file instead [skip ci] ([d2ebccf](https://github.com/dafyddj/tmp-test-template-formula/commit/d2ebccf27d42feec24da54b2f884d0ba2faa8477))
* **contributing:** separate `BREAKING CHANGE` under its own heading ([ee053d7](https://github.com/dafyddj/tmp-test-template-formula/commit/ee053d7b8c4cbb09c9a97b5ec835688a6069ac99))
* **contributing:** update with sub-headings and `commitlint` details ([ea2c9a4](https://github.com/dafyddj/tmp-test-template-formula/commit/ea2c9a403d2eb08cd8c2e07b9c0b98fff1da901e))
* **convert-formula.sh:** add usage guide ([539a335](https://github.com/dafyddj/tmp-test-template-formula/commit/539a335f8b01ffb3944b742cc2f5852a718546dd))
* fix whitespace ([d98d98f](https://github.com/dafyddj/tmp-test-template-formula/commit/d98d98f4da1096f4c60c5ec5c15d56d1945c9f50))
* **index:** add `CONTRIBUTING` to the `toctree` ([0c98e67](https://github.com/dafyddj/tmp-test-template-formula/commit/0c98e67096be74abb5e20de5c1168d2716ee586f))
* **issues:** provide `Bug report` & `Feature request` templates ([f90f1f6](https://github.com/dafyddj/tmp-test-template-formula/commit/f90f1f6326db6332c1c3d05b6d659550dcd8a1d2))
* **issues:** use `Meta` instead of `Optional` as suggested ([65cadb4](https://github.com/dafyddj/tmp-test-template-formula/commit/65cadb4ba886cb452934687b87fcaabee7c53584))
* **issues:** use larger headings (from level 4 to level 3) ([53e7b75](https://github.com/dafyddj/tmp-test-template-formula/commit/53e7b75c7928299f4c7d2d30fc6fa8fd8b2579ba))
* **libtofs:** explain usage of sub-directory for components ([42a75d9](https://github.com/dafyddj/tmp-test-template-formula/commit/42a75d99ee78091111a8b05310655f1d370e6c93))
* **map.jinja:** fix `rst-lint` violation [skip ci] ([e43d6ce](https://github.com/dafyddj/tmp-test-template-formula/commit/e43d6ce83f4cacfd70a5df3bbc53e22a9b442b24))
* **map.jinja:** fix path to post-map.jinja in docs ([d64cd75](https://github.com/dafyddj/tmp-test-template-formula/commit/d64cd75f62b7ad20f61de85e19534da492f55eda))
* **map.jinja:** make section headings consistent with other docs ([40277fc](https://github.com/dafyddj/tmp-test-template-formula/commit/40277fc582a62d2255b478fb0b880eda1f46d77a))
* **map:** update comments in `os*.yaml` after adding `osarchmap` ([d71a258](https://github.com/dafyddj/tmp-test-template-formula/commit/d71a258a2f043bb27dc12517556ed2488b8efe20))
* move contributing sections and links to ease adaptation ([741896d](https://github.com/dafyddj/tmp-test-template-formula/commit/741896dc1ef7271bb65876d8ced91479bcc09f52))
* **pillar.example:** fix TOFS comment to explain the default path [skip ci] ([fde5063](https://github.com/dafyddj/tmp-test-template-formula/commit/fde5063e15d497e133c653f71280e72a000689fa))
* **pillar.example:** improve TOFS comment to explain the default path [skip ci] ([27d2fe4](https://github.com/dafyddj/tmp-test-template-formula/commit/27d2fe45dd301cdd3f47f3c6e3a87acd3d432fa4))
* **readme:** add Read the Docs build status badge ([f47797d](https://github.com/dafyddj/tmp-test-template-formula/commit/f47797d1fc4b7c6314d22823211bb83f575611ed))
* **readme:** add suggested improvement to `template.service.clean` ([bf1039c](https://github.com/dafyddj/tmp-test-template-formula/commit/bf1039ca99a86ee572d39a046d52b916f401052d))
* **readme:** add testing requirements section (from `vault-formula`) ([e04413e](https://github.com/dafyddj/tmp-test-template-formula/commit/e04413e52dc56ed42daab30709e21ad8346402e7))
* **readme:** add testing section based on `postgres-formula` ([c309d5f](https://github.com/dafyddj/tmp-test-template-formula/commit/c309d5f6834feab90c0ffdb3e3ad43b168bfd149))
* **readme:** convert note into a heading ([5f2d789](https://github.com/dafyddj/tmp-test-template-formula/commit/5f2d7894abeb119b480ebc18d18afb9a7a38c8ba))
* **readme:** describe the new “template.subcomponent” states ([6b595cd](https://github.com/dafyddj/tmp-test-template-formula/commit/6b595cd8cebf33d631e477a83b860b32bf278b41))
* **readme:** fix typos ([007159a](https://github.com/dafyddj/tmp-test-template-formula/commit/007159ac415ff62bb931478a081ade6dd0ca6e3d))
* **readme:** move under `docs` subdir to access in both GitHub and RTD ([c92f674](https://github.com/dafyddj/tmp-test-template-formula/commit/c92f67446996e345fc7df804922fcc6bbf735544))
* **readme:** show only one level in table of contents ([446b815](https://github.com/dafyddj/tmp-test-template-formula/commit/446b81595822a54792cfbaf23fade20e652d7062))
* **readme:** tidy headings ([d931ed1](https://github.com/dafyddj/tmp-test-template-formula/commit/d931ed1672962d53690988ad317ae9aabc013b55))
* **readme:** update heading markers for consistency ([5a2bea8](https://github.com/dafyddj/tmp-test-template-formula/commit/5a2bea8fddd95f33645702823c278bee91f3e350))
* **readme:** update link to `CONTRIBUTING` [skip ci] ([ed61d09](https://github.com/dafyddj/tmp-test-template-formula/commit/ed61d09af0258c138c1b70ed51b26c165b72ab94))
* **reamde:** have special notes section ([c68aed5](https://github.com/dafyddj/tmp-test-template-formula/commit/c68aed500b6af0cd6f2a9876c327af737f360376))
* **rtd:** add basic `docs/conf.py` to allow additional customisation ([18d3924](https://github.com/dafyddj/tmp-test-template-formula/commit/18d3924dcb111ad5c7af57a3f0418243d55329c6))
* **rtd:** add basic `index.rst` to allow RTD to produce docs ([f02139f](https://github.com/dafyddj/tmp-test-template-formula/commit/f02139f3ac05baf4183b03ee6c7c69bb42902041))
* **rtd:** add comment to CSS file for overriding in-use Sphinx theme ([f237364](https://github.com/dafyddj/tmp-test-template-formula/commit/f2373641b4590c177cd7f59a766f42c149c6f833))
* **rtd:** clean up numerous issues and inconsistencies ([ad5a8b8](https://github.com/dafyddj/tmp-test-template-formula/commit/ad5a8b84bfe7a5ae46796a502e1759b3916c7d72))
* **rtd:** use internal link targets at the top of each `.rst` file ([da09528](https://github.com/dafyddj/tmp-test-template-formula/commit/da095281a836738b438a9b664af614e326e20e22))
* **semantic-release:** add list of semantic-release compatible formulas ([97b19b9](https://github.com/dafyddj/tmp-test-template-formula/commit/97b19b9af0739606608a6a6ebc6a08b841010ab4))
* **tofs:** add more sub-headings to ease document navigation ([2c5dc21](https://github.com/dafyddj/tmp-test-template-formula/commit/2c5dc210635be099429cff18c7204e39eeb9014f))
* **tofs:** apply language formatting to source code blocks ([0638413](https://github.com/dafyddj/tmp-test-template-formula/commit/0638413a59d7039443a494c411e1a641683b6a71))
* **tofs:** ensure merged will all recent changes ([6a614d9](https://github.com/dafyddj/tmp-test-template-formula/commit/6a614d967f02fcc6ab436f3ad7af079a7dbef5d1))
* **tofs:** explain how all parts of the `source` can be customised ([2f82eb5](https://github.com/dafyddj/tmp-test-template-formula/commit/2f82eb54affbee3db3fb58659a0c7c158a1a1d89)), closes [#44](https://github.com/dafyddj/tmp-test-template-formula/issues/44)
* **tofs:** improve general use of language ([5105d29](https://github.com/dafyddj/tmp-test-template-formula/commit/5105d293d0e48e89bd99179208e6c6eff5d18bca))
* **tofs:** incorrect path for “source_files” lookup key ([a76f659](https://github.com/dafyddj/tmp-test-template-formula/commit/a76f659e9d558751bdb0a188f424508b665189d0))
* **tofs:** remove whitespace from blank line ([0881b7d](https://github.com/dafyddj/tmp-test-template-formula/commit/0881b7daf1e487471d81a3d9bdccddbed9563e00))
* **tofs:** replace existing `.md` with `.rst` and add to RTD ([fd68168](https://github.com/dafyddj/tmp-test-template-formula/commit/fd68168cce4155f91f6b22619c8dfc9b6339066a))
* **tofs:** update from `nginx-formula` ([23a221e](https://github.com/dafyddj/tmp-test-template-formula/commit/23a221ef013e82e3fcf45c9a4a3c1ccee258a96e))
* **tofs:** update the `files_switch` section for the updated macro ([788f732](https://github.com/dafyddj/tmp-test-template-formula/commit/788f732368d6fb380ec902521c2b1e7c5ad4445a))
* **tofs:** use `{%-` for all Jinja statements ([4348df8](https://github.com/dafyddj/tmp-test-template-formula/commit/4348df89546f8c4824d9f1860f38a8c4faccca7a))
* **tofs:** use `literalinclude` of `macros.jinja` instead of code dupe ([3f0071b](https://github.com/dafyddj/tmp-test-template-formula/commit/3f0071b72ba121db131ba70b2a455fefeadc1355))
* **tofs:** use table to list authorship ([2f0e20f](https://github.com/dafyddj/tmp-test-template-formula/commit/2f0e20f4493f51821d0213d9437e332c456f2125))
* **yaml:** os*.yaml map files needs at least an empty dict ([dd99750](https://github.com/dafyddj/tmp-test-template-formula/commit/dd997506c0bc64e967892df3de64e26e0c3842d4))

### Testing

* **_mapdata:** add verification file for `debian-11` [skip ci] ([98edfd3](https://github.com/dafyddj/tmp-test-template-formula/commit/98edfd3ac403353e9bd7d1d335e9ab48af3f1892))
* **_mapdata:** add verification file for `fedora-34` [skip ci] ([79587c4](https://github.com/dafyddj/tmp-test-template-formula/commit/79587c422c0d30dc8ce203021afc63b62d4cbdf3))
* **_mapdata:** add verification file for `fedora-35` [skip ci] ([6f02d2c](https://github.com/dafyddj/tmp-test-template-formula/commit/6f02d2c28a7d3fe1449b93d862d02268344aa475))
* **_mapdata:** add verification file for `fedora-36` [skip ci] ([4a38a29](https://github.com/dafyddj/tmp-test-template-formula/commit/4a38a292d66563984505ed082166b25f831fb460))
* **_mapdata:** add verification file for `ubuntu-22` [skip ci] ([9349c83](https://github.com/dafyddj/tmp-test-template-formula/commit/9349c838742a1396c092311e2529e80d3d76fabd))
* **_mapdata:** add verification files for Fedora 33 & Tumbleweed ([3347b85](https://github.com/dafyddj/tmp-test-template-formula/commit/3347b85c928cebe8b0c376eae654e67e01730260))
* **_mapdata:** fix existing verification files ([6bbafed](https://github.com/dafyddj/tmp-test-template-formula/commit/6bbafedd1f9ad6e6b659ab6ab4b1736b5c4d9a66))
* **_mapdata:** update for `_mapdata/init.sls` change ([50162ad](https://github.com/dafyddj/tmp-test-template-formula/commit/50162adad7119285a649321b5f66710974a7983d))
* **`services_spec`:** remove temporary `suse` conditional ([00d4a77](https://github.com/dafyddj/tmp-test-template-formula/commit/00d4a77f17083da5f0d6cd0b70bdedc1fef1e32d))
* add CI test of conversion script ([7ad85ae](https://github.com/dafyddj/tmp-test-template-formula/commit/7ad85ae0db21888921efabbc88bcafbc65e5bd21))
* **alma+rocky:** add platforms (based on CentOS 8) [skip ci] ([ec7ede0](https://github.com/dafyddj/tmp-test-template-formula/commit/ec7ede04077566dd3bc69ac3032b09ffcc3b7876))
* **github-actions:** check GitHub Actions using `check-jsonschema` ([1600e5f](https://github.com/dafyddj/tmp-test-template-formula/commit/1600e5f92695bcd377aba31f7f877f6c6dff89da))
* **gitlab-ci:** check GitLab CI config using `check-jsonschema` ([670c139](https://github.com/dafyddj/tmp-test-template-formula/commit/670c139f6b84667c9e9259ddf661f366753f18d4))
* **inspec:** `system.rb` must call parent class initialisation ([1ff9ab1](https://github.com/dafyddj/tmp-test-template-formula/commit/1ff9ab15f23ba9f3b78a1b8f9dcef7a062e2b192))
* **inspec:** disable `service`-based tests for `opensuse-leap-15` ([848c2ad](https://github.com/dafyddj/tmp-test-template-formula/commit/848c2ad2c76f5f107b7c12c0991145dbdfc1e26f))
* **inspec:** readme for default profile & os-name depreciated ([3fa7bce](https://github.com/dafyddj/tmp-test-template-formula/commit/3fa7bcee1bdfce90d563514f0a0bab5a16a40219))
* **inspec:** share library to access some minion informations ([64c2b6c](https://github.com/dafyddj/tmp-test-template-formula/commit/64c2b6cdae1ad91959b5c0fe67863a529a070428))
* **inspec:** update `supports` for all platforms added ([42f93b3](https://github.com/dafyddj/tmp-test-template-formula/commit/42f93b38230ea2dd09a1cb702aa3eb25f0b045f1))
* **inspec:** verify `map.jinja` dump ([3dc28bf](https://github.com/dafyddj/tmp-test-template-formula/commit/3dc28bfb3453079deca899352ecdff30daeb42f5))
* **inspec:** verify subcomponent configuration file ([fd55e03](https://github.com/dafyddj/tmp-test-template-formula/commit/fd55e03692f7ac9687d3d00da56854e7ed62ee7e))
* **kitchen:** avoid lengthy waits for containers ([2db5865](https://github.com/dafyddj/tmp-test-template-formula/commit/2db58656b4dbccea0b50d3debdf2da9859f86ed6))
* **kitchen:** drop timeout to `60` seconds ([2817f52](https://github.com/dafyddj/tmp-test-template-formula/commit/2817f525cb7b1efa2e1f5c6c181437350b4a6bf0))
* **libtofs:** “tofs.files_switch” lookup can return a list ([13f1728](https://github.com/dafyddj/tmp-test-template-formula/commit/13f1728c279bc5b1cf69b3bd8d397bf6fec50d20))
* **map:** standardise `map.jinja` verification ([4c8cf32](https://github.com/dafyddj/tmp-test-template-formula/commit/4c8cf32db1824fb9841996d758d19c563f5414c5))
* **oracle:** add InSpec configuration for `oraclelinux` ([c4b66d8](https://github.com/dafyddj/tmp-test-template-formula/commit/c4b66d8f0b5666261b43ee923565cc516b7fb92f))
* **osarch:** add unit test for osarch ([1be2052](https://github.com/dafyddj/tmp-test-template-formula/commit/1be20524cf05cde90d133396ececa6ef18439a71))
* **pillar:** use static test/salt/pillar/top.sls ([7708e12](https://github.com/dafyddj/tmp-test-template-formula/commit/7708e1292303431d9ac4a46f0c4123cc95b98bc6))
* **platform_finger:** extract from shared library ([d68ed45](https://github.com/dafyddj/tmp-test-template-formula/commit/d68ed45109aa1274c6bf236db30758d795a3ba2a))
* **pre-commit:** check for Git merge conflict markers ([895d4f9](https://github.com/dafyddj/tmp-test-template-formula/commit/895d4f90ebd851c74b1dd0b121f3a7f9d8618771))
* **pre-commit:** check JavaScript files using standardJS ([b0c7df4](https://github.com/dafyddj/tmp-test-template-formula/commit/b0c7df414a53b6a5da970170bb66dd7ffa75ae30))
* **pre-commit:** switch to using `pre-commit`'s built-in file filtering ([46130c4](https://github.com/dafyddj/tmp-test-template-formula/commit/46130c4c092c89dd372f2a3f3b14e7568375d067))
* **pre-commit:** update `pre-commit` hooks ([2bd3ef9](https://github.com/dafyddj/tmp-test-template-formula/commit/2bd3ef9a1835db081a86d3ea0f4434e3e17ce1a7))
* **pre-commit:** update deprecated stage name ([a82b2ed](https://github.com/dafyddj/tmp-test-template-formula/commit/a82b2eda6d7968689975cf0bdadbff19c4841ed5))
* **rstcheck:** ignore Markdown-style links as false positives ([b2c28aa](https://github.com/dafyddj/tmp-test-template-formula/commit/b2c28aa906fcce406b01523e7b7eccd04e658984))
* **rubocop:** switch to using `pre-commit`'s built-in file filtering ([c3b4c14](https://github.com/dafyddj/tmp-test-template-formula/commit/c3b4c1407051cda4421914921947f17de3101c6b))
* **rubocop:** use `AllowedMethods` not deprecated `IgnoredMethods` ([9261a27](https://github.com/dafyddj/tmp-test-template-formula/commit/9261a27794137490a8810522d6541a62a75a2011))
* **share:** remove unnecessary hostname mangling ([194aa97](https://github.com/dafyddj/tmp-test-template-formula/commit/194aa97dff47acd59076865489914b4148b1b76d))
* **share:** standardise with latest changes [skip ci] ([dab2f34](https://github.com/dafyddj/tmp-test-template-formula/commit/dab2f34c587ea6194351c768e9ba141744536607))
* standardise use of `share` suite & `_mapdata` state [skip ci] ([bbe1c78](https://github.com/dafyddj/tmp-test-template-formula/commit/bbe1c7840990790eb2df564e96cc9b465093eb62))
* **system.rb:** add support for `mac_os_x` [skip ci] ([d46507b](https://github.com/dafyddj/tmp-test-template-formula/commit/d46507ba82b2a197e1275d7c258f7245862c2662))
* **system:** add `build_platform_codename` [skip ci] ([65cf22c](https://github.com/dafyddj/tmp-test-template-formula/commit/65cf22c436903a65f93b9f5e708d8639499d542b))
* update `commitlint` hook to v19.8.1 ([0d060d9](https://github.com/dafyddj/tmp-test-template-formula/commit/0d060d93e3c54f9ed2ebb620d6b0ff62691c05e0))
* **yamllint:** allow for long words and Renovate-specific comments ([43a31a3](https://github.com/dafyddj/tmp-test-template-formula/commit/43a31a39d6bd8e8a4121e07d6fb718f8a24f5b1e))
* **yamllint:** exclude auto-generated Copier files from linting ([6cda6ad](https://github.com/dafyddj/tmp-test-template-formula/commit/6cda6adc52c836406eaeee618ae2228db3e0a0bc))

### Style Changes

* **default.sls:** fix minor typo ([3d1581e](https://github.com/dafyddj/tmp-test-template-formula/commit/3d1581e72611bfdac1ae14c57b69921c45f6b886))
* fix typo ([68d5ba0](https://github.com/dafyddj/tmp-test-template-formula/commit/68d5ba0507ad0d10d51934f68fcea78470003669))
* **gitlab-ci:** order instances alphabetically for consistency ([06cfa97](https://github.com/dafyddj/tmp-test-template-formula/commit/06cfa9739a2cf12ef0120c3ca0564f613e2fe001))
* **indent:** fix indentation ([34d1307](https://github.com/dafyddj/tmp-test-template-formula/commit/34d130795c7f37d598543ba97b802aae761ab710))
* **inspec:** fix whitespace ([1df9861](https://github.com/dafyddj/tmp-test-template-formula/commit/1df98610848bff149cb7c55549d691ca960005f9))
* **inspec:** match current practices for file and control names ([aa8a58b](https://github.com/dafyddj/tmp-test-template-formula/commit/aa8a58b715fec48b256ff0aa8a0b697b1ae20399))
* **libsaltcli:** fix comments to jinja comments ([e1735f4](https://github.com/dafyddj/tmp-test-template-formula/commit/e1735f47f8e7af13d8d3d4be9206851560e30c52))
* **libtofs.jinja:** use Black-inspired Jinja formatting [skip ci] ([55bc69a](https://github.com/dafyddj/tmp-test-template-formula/commit/55bc69a2b194874ceb594c93c8750c320239103c))
* **map:** use `-` for each Jinja block ([64e3834](https://github.com/dafyddj/tmp-test-template-formula/commit/64e383474f7a1d6f2923b72780e2ad5162b3eefa))

### Continuous Integration

* **3003.1:** update inc. AlmaLinux, Rocky & `rst-lint` [skip ci] ([be3ee0b](https://github.com/dafyddj/tmp-test-template-formula/commit/be3ee0be5148ab598a613342e902284ffb547628))
* add `arch-master` to matrix and update `.travis.yml` [skip ci] ([7e74001](https://github.com/dafyddj/tmp-test-template-formula/commit/7e74001c05292eb313a8f4a539784cdf94e232a0))
* add Debian 11 Bullseye & update `yamllint` configuration [skip ci] ([e14f830](https://github.com/dafyddj/tmp-test-template-formula/commit/e14f83019a97ea49b4b056c6a9c2f51cac7887a9))
* add mapdata for new os ([a1bdd12](https://github.com/dafyddj/tmp-test-template-formula/commit/a1bdd126089d1e6d222580fe931e2632a9df1ed5))
* allow failures on all `master` test instances ([aeb7926](https://github.com/dafyddj/tmp-test-template-formula/commit/aeb7926b927f2c7c9f02442f133f680b45f58dba))
* **commitlint:** ensure `upstream/master` uses main repo URL [skip ci] ([e476d5a](https://github.com/dafyddj/tmp-test-template-formula/commit/e476d5a567d90592ea32f193d2264de59d261711))
* **commitlint:** update action versions ([c69928d](https://github.com/dafyddj/tmp-test-template-formula/commit/c69928d2495966daaf4ca8bf82dd53e999e1739c))
* **gemfile.lock:** add to repo with updated `Gemfile` [skip ci] ([d798928](https://github.com/dafyddj/tmp-test-template-formula/commit/d79892867549e13737a2d0f887a1388ec45704af))
* **gemfile+lock:** use `ssf` customised `inspec` repo [skip ci] ([3c7fb0f](https://github.com/dafyddj/tmp-test-template-formula/commit/3c7fb0fca0498d7fd5b2e23c763a14e9258c051f))
* **gemfile+lock:** use `ssf` customised `kitchen-docker` repo [skip ci] ([23c2bb2](https://github.com/dafyddj/tmp-test-template-formula/commit/23c2bb2dc26f4c1600d484312a79dd0af0e232d7))
* **gemfile:** restrict `train` gem version until upstream fix [skip ci] ([1b6164f](https://github.com/dafyddj/tmp-test-template-formula/commit/1b6164fc4a5bda44e8cb1104039606603dab4c2e))
* **gemfile:** update `kitchen-salt` version ([ad31c32](https://github.com/dafyddj/tmp-test-template-formula/commit/ad31c32b06deafa8fdadfa710fbeaed8cae3f58e))
* get this working ([e5b0be4](https://github.com/dafyddj/tmp-test-template-formula/commit/e5b0be45bc197ee1e8d4af6e595de76cfccb558d))
* **gitlab-ci:** add `rubocop` linter (with `allow_failure`) [skip ci] ([4c300d0](https://github.com/dafyddj/tmp-test-template-formula/commit/4c300d01cb909f2fbed07d39b22c06198c304cdf))
* **gitlab-ci:** fix test conversion job (reset back to [#249](https://github.com/dafyddj/tmp-test-template-formula/issues/249)) [skip ci] ([6ea1cc2](https://github.com/dafyddj/tmp-test-template-formula/commit/6ea1cc2f4066796ca00c2bf0cb630ef4302df660))
* **gitlab-ci:** improve `pre-commit` caching ([fae68d8](https://github.com/dafyddj/tmp-test-template-formula/commit/fae68d8339731bfaf88be2762d3ee8dde4a6b758))
* **gitlab-ci:** improve caching for `bundler` and `test_conversion` job ([6833620](https://github.com/dafyddj/tmp-test-template-formula/commit/683362093eddd47f0d2b16d49a059afe78e42781))
* **gitlab-ci:** optimise test instance caching ([efbd8c6](https://github.com/dafyddj/tmp-test-template-formula/commit/efbd8c682086aade92671e083496004888c226ff))
* **gitlab-ci:** remove `py3` from instance names ([076a6cb](https://github.com/dafyddj/tmp-test-template-formula/commit/076a6cb875a880869685fe6fea31ac3a7f939203))
* **gitlab-ci:** remove amended commit due to `coqbot` ([d14b2cf](https://github.com/dafyddj/tmp-test-template-formula/commit/d14b2cf08f5d6e883a36cb66f8c1fb9191cd1664))
* **gitlab-ci:** remove deprecated keyword `only` for stage `release ([e44296e](https://github.com/dafyddj/tmp-test-template-formula/commit/e44296e473f142f41c36cecbd252bf172b7174c7))
* **gitlab-ci:** run `commitlint` in `pre-commit` job ([a5a6962](https://github.com/dafyddj/tmp-test-template-formula/commit/a5a6962840a35462482425d6c93abde63504d8a2))
* **gitlab-ci:** simplify list of TestKitchen instances ([888286a](https://github.com/dafyddj/tmp-test-template-formula/commit/888286a82a7ec53c9ce5022d70368a447466881c))
* **gitlab-ci:** specify version for `dind` service image ([235a963](https://github.com/dafyddj/tmp-test-template-formula/commit/235a963b6b771ae99543f3ddb0b2031d73936d46))
* **gitlab-ci:** switch to image `techneg/ci-semantic-release` ([35c2ed6](https://github.com/dafyddj/tmp-test-template-formula/commit/35c2ed6b3da9f04aefec605ee4a05bab9c99ee53))
* **gitlab-ci:** update `dind-ruby-bionic` (use Python 3.7 for pre-commit) ([8ff2152](https://github.com/dafyddj/tmp-test-template-formula/commit/8ff2152b32262fe2082f68e42532f3c0178f55b0))
* **gitlab-ci:** use GitLab CI as Travis CI replacement ([0403f62](https://github.com/dafyddj/tmp-test-template-formula/commit/0403f62c7780a8a449617003c5363118a8b6ecd6))
* **gitlab-ci:** use Node `16.x` for `pre-commit` in test conversion job ([a1a46ae](https://github.com/dafyddj/tmp-test-template-formula/commit/a1a46ae38995f1506c3574c7818cfc8fcc887d6c))
* **gitlab:** update `dind-ruby-bionic` with ruby 2.7.1 ([b2fe67a](https://github.com/dafyddj/tmp-test-template-formula/commit/b2fe67a79d582313b6fd2468441141eae2705ae2))
* ignore `yamllint rule:line-length` for Docker images ([ec26bf1](https://github.com/dafyddj/tmp-test-template-formula/commit/ec26bf1adba0833df44170978ae65492a2976b80))
* **kitchen+ci:** update with `3004` pre-salted images/boxes [skip ci] ([ea37971](https://github.com/dafyddj/tmp-test-template-formula/commit/ea379716bea3d9d93a88671b8c0ae368033dcd62))
* **kitchen+ci:** update with latest `3003.2` pre-salted images [skip ci] ([1b8604d](https://github.com/dafyddj/tmp-test-template-formula/commit/1b8604dd02907ea6da50c0ab539dd510f9fb755b))
* **kitchen+ci:** update with latest CVE pre-salted images [skip ci] ([6c5809d](https://github.com/dafyddj/tmp-test-template-formula/commit/6c5809d067ae5ae7db52c17bda30b0cd133b7966))
* **kitchen+ci:** use latest pre-salted images (after CVE) [skip ci] ([6453145](https://github.com/dafyddj/tmp-test-template-formula/commit/6453145da16ab73c7307d14a5b864a91a5573c68))
* **kitchen+gitlab-ci:** use latest pre-salted images [skip ci] ([00823a2](https://github.com/dafyddj/tmp-test-template-formula/commit/00823a2d276648d184c92308f7829d0fdeefe0ba))
* **kitchen+gitlab:** adjust matrix to add `3003` [skip ci] ([c99c5a1](https://github.com/dafyddj/tmp-test-template-formula/commit/c99c5a1b68cfe2374f38e1577515efd73c58a610))
* **kitchen+gitlab:** remove OpenSUSE 15.5 (EOL) ([54bdd66](https://github.com/dafyddj/tmp-test-template-formula/commit/54bdd661f8453ee2d4fce5d0be83e1b67b4a92f6))
* **kitchen+gitlab:** remove Ubuntu 16.04 & Fedora 32 (EOL) [skip ci] ([858ef8a](https://github.com/dafyddj/tmp-test-template-formula/commit/858ef8a2b7097421a5073b0963c8b29ec3840bf3))
* **kitchen+gitlab:** update for new pre-salted images [skip ci] ([801be3d](https://github.com/dafyddj/tmp-test-template-formula/commit/801be3d974abdc28e786d4ac462f018db45a891b))
* **kitchen+gitlab:** update for new pre-salted images [skip ci] ([fd34718](https://github.com/dafyddj/tmp-test-template-formula/commit/fd347183f992f2d0511986744f65c715445d7c5e))
* **kitchen+travis:** add new platforms [skip ci] ([111a20b](https://github.com/dafyddj/tmp-test-template-formula/commit/111a20b47d89d275ce4ff5213656d6828acb2760))
* **kitchen+travis:** adjust matrix to add `3000.2` & remove `2018.3` [skip ci] ([efd8797](https://github.com/dafyddj/tmp-test-template-formula/commit/efd8797e66bbe45d58a7155283b6ef47bb3fb7a4))
* **kitchen+travis:** adjust matrix to add `3000.3` [skip ci] ([19ae826](https://github.com/dafyddj/tmp-test-template-formula/commit/19ae82632ece95047b535390bd2325fb30a09af7))
* **kitchen+travis:** adjust matrix to add `3000` & remove `2017.7` [skip ci] ([f81c372](https://github.com/dafyddj/tmp-test-template-formula/commit/f81c372dfe12d42139275fc8c9e7aad1b6eec976))
* **kitchen+travis:** adjust matrix to update `3000` to `3000.1` [skip ci] ([f48a727](https://github.com/dafyddj/tmp-test-template-formula/commit/f48a7275644d2baef06adb0d8e74b3c19fd2d8a0))
* **kitchen+travis:** disable `debian-8` due to `2019.2` installation bug ([178c710](https://github.com/dafyddj/tmp-test-template-formula/commit/178c7103f3e53e0a51132c4698e7ce5fc24999bf))
* **kitchen+travis:** fix `centos6` suite and rename to `upstart` ([97309c6](https://github.com/dafyddj/tmp-test-template-formula/commit/97309c6f4d6b18723ec5492564b1344155960ae0))
* **kitchen+travis:** implement new distro-python-salt_version matrix ([bd4792d](https://github.com/dafyddj/tmp-test-template-formula/commit/bd4792d260e041d62b35d50f19baca83cd5a4925))
* **kitchen+travis:** modify matrix to include `develop` platform ([7b5d4ff](https://github.com/dafyddj/tmp-test-template-formula/commit/7b5d4ffadf0349495d3735594b3a50a2b905d1e3))
* **kitchen+travis:** remove `master-py2-arch-base-latest` [skip ci] ([d693f9d](https://github.com/dafyddj/tmp-test-template-formula/commit/d693f9dabf722946a978c64ed4fbfa03653e828c))
* **kitchen+travis:** replace EOL pre-salted images ([42ab22c](https://github.com/dafyddj/tmp-test-template-formula/commit/42ab22c13fa4269a91fcea5471e25fa29d7acbd8))
* **kitchen+travis:** upgrade matrix after `2019.2.2` release [skip ci] ([d0e07b8](https://github.com/dafyddj/tmp-test-template-formula/commit/d0e07b88834f68cc81ce4de34c14a880347fc497))
* **kitchen+travis:** use `debian:jessie-backports` as `debian-8` ([1b9d249](https://github.com/dafyddj/tmp-test-template-formula/commit/1b9d2493c94b4dbeb21ea5e9c6596195cf3ce5cc)), closes [#50](https://github.com/dafyddj/tmp-test-template-formula/issues/50)
* **kitchen+travis:** use `tiamat` pre-salted images ([3a63304](https://github.com/dafyddj/tmp-test-template-formula/commit/3a63304f13d717fc28efbb06252ffde421ab3621))
* **kitchen+travis:** use latest pre-salted images ([91ef13b](https://github.com/dafyddj/tmp-test-template-formula/commit/91ef13b1e13d8f726ab2449433290bfbcb17ce05))
* **kitchen:** add Bundler binstub for Kitchen ([7bb7c53](https://github.com/dafyddj/tmp-test-template-formula/commit/7bb7c532b9cc963b8a0f8a5e9204b7fc916f1f07))
* **kitchen:** avoid using bootstrap for `master` instances ([6ecdb99](https://github.com/dafyddj/tmp-test-template-formula/commit/6ecdb99f83b807b4679dc6534ae425b97eefbe54))
* **kitchen:** change `log_level` to `debug` instead of `info` ([1b929ff](https://github.com/dafyddj/tmp-test-template-formula/commit/1b929ff625ece48e6c0eb2558e17ee341744ee5f))
* **kitchen:** check for repos updates before trying package installation ([b632383](https://github.com/dafyddj/tmp-test-template-formula/commit/b6323834e592920cbf414549f02fa6e09ff3760a))
* **kitchen:** execute `_madata` state ([31e1096](https://github.com/dafyddj/tmp-test-template-formula/commit/31e1096adda4c23f77b797f35c465ba09043b3a6))
* **kitchen:** improve comments about `opensuse` problems encountered ([c246939](https://github.com/dafyddj/tmp-test-template-formula/commit/c2469396669e3dcc1f3d0d2549ae1a458afafeba))
* **kitchen:** install required packages to bootstrapped `opensuse` [skip ci] ([1cfed60](https://github.com/dafyddj/tmp-test-template-formula/commit/1cfed60a13842c77049683ea48234944819b4774))
* **kitchen:** move `provisioner` block & update `run_command` [skip ci] ([29df15e](https://github.com/dafyddj/tmp-test-template-formula/commit/29df15e21ca972915b4ac5718c65c9aa6305eaff))
* **kitchen:** specify `image` explicitly for each platform ([b25fbdc](https://github.com/dafyddj/tmp-test-template-formula/commit/b25fbdc2a5d2a1f425ca24b5a99f36dcec75ef82))
* **kitchen:** use `debian-10-master-py3` instead of `develop` [skip ci] ([14ebf92](https://github.com/dafyddj/tmp-test-template-formula/commit/14ebf928bc07cefa086523e63bed5df7c2879e9b))
* **kitchen:** use `develop` image until `master` is ready (`amazonlinux`) [skip ci] ([42482d7](https://github.com/dafyddj/tmp-test-template-formula/commit/42482d7f9b77f5d34417e25233a9f385075feace))
* **kitchen:** use `pillars_from_directories` under `provisioner` ([5f80cf2](https://github.com/dafyddj/tmp-test-template-formula/commit/5f80cf2b7dc9dc90cd2de2121787c3b7b5efc6bf))
* **kitchen:** use `salt-minion` version of `opensuse` to ensure tests run ([99b073a](https://github.com/dafyddj/tmp-test-template-formula/commit/99b073a7ceaa4cd15501b7495ebb0a714ceff116))
* **kitchen:** use `saltimages` Docker Hub where available [skip ci] ([eab21c3](https://github.com/dafyddj/tmp-test-template-formula/commit/eab21c39fb180d3cf3be93a4ae0678b1fbe6357d))
* **kitchen:** use bootstrapped `opensuse` images until `2019.2.2` [skip ci] ([0467bdf](https://github.com/dafyddj/tmp-test-template-formula/commit/0467bdf8b51dff593bd7f33bdfeae067d45c6094))
* **kitchen:** use pre-salted images instead ([2855ed6](https://github.com/dafyddj/tmp-test-template-formula/commit/2855ed6cf1156831df971d1dab2db8013733f3b8))
* **platform:** add `arch-base-latest` ([042e8e2](https://github.com/dafyddj/tmp-test-template-formula/commit/042e8e2331af2d14187f9cf97676fd19b68acc68))
* **pre-commit:** add to formula [skip ci] ([fd89d62](https://github.com/dafyddj/tmp-test-template-formula/commit/fd89d62ec656dc3e6f84b9834860bf51359452f5))
* **pre-commit:** enable/disable `rstcheck` as relevant [skip ci] ([219e6b7](https://github.com/dafyddj/tmp-test-template-formula/commit/219e6b71c85f06657564c87ba58877cfc5ebe511))
* **pre-commit:** finalise `rstcheck` configuration [skip ci] ([e78aa0c](https://github.com/dafyddj/tmp-test-template-formula/commit/e78aa0cb784752ae699196c6309fe93bf223a306))
* **pre-commit:** update hook for `rubocop` [skip ci] ([978a7e7](https://github.com/dafyddj/tmp-test-template-formula/commit/978a7e7cd04c00fe6e7b5d113926683a86534094))
* **proxy:** allow rubygems proxy in gemfile ([7109cfd](https://github.com/dafyddj/tmp-test-template-formula/commit/7109cfd411804514607a70edc3339e011e1db1cc))
* remove EOL images & allow failure of `amazonlinux-2` ([6e6d524](https://github.com/dafyddj/tmp-test-template-formula/commit/6e6d524ea4f2bf55115be2517c3556a7477138b5))
* **renovate:** disable Bundler (Ruby Gems) updates ([8a18188](https://github.com/dafyddj/tmp-test-template-formula/commit/8a1818868966d51a4faae4aab30d0de4b4f0eb3f))
* **renovate:** enable and group GitHub Actions updates ([0bb9c03](https://github.com/dafyddj/tmp-test-template-formula/commit/0bb9c033f635355cf6207ab5b83039742fbae2d2))
* **renovate:** enable and group Pre-commit hook non-major updates ([d21a192](https://github.com/dafyddj/tmp-test-template-formula/commit/d21a192c1c1ad062f631a7da9a1e160ed4866460))
* **renovate:** enable Bundler (Ruby Gems) updates ([2781f77](https://github.com/dafyddj/tmp-test-template-formula/commit/2781f77703d88b09973a83818abb81087a68e670))
* **renovate:** group GitLab CI Docker images together ([0a8dd28](https://github.com/dafyddj/tmp-test-template-formula/commit/0a8dd28c355f77f019fc595e5fc9c5883c84d46d))
* **renovate:** improve wording ([079ec01](https://github.com/dafyddj/tmp-test-template-formula/commit/079ec0189873b15f3e9f691b9ac0fa6f3b2d007a))
* **renovate:** include digest updates in GitLab images group ([6146090](https://github.com/dafyddj/tmp-test-template-formula/commit/614609094b522f4ec711f5690532934bec8878ce))
* **renovate:** initial commit of basic Renovate config ([bd7464b](https://github.com/dafyddj/tmp-test-template-formula/commit/bd7464b80705a2b26a1f902ba9f1ff270680239f))
* **renovate:** limit schedule to Tuesdays before 6AM ([9b3d017](https://github.com/dafyddj/tmp-test-template-formula/commit/9b3d017bbd678febd2285bf6a39c12d2b59f734e))
* **renovate:** use `groupManager` preset ([4061b00](https://github.com/dafyddj/tmp-test-template-formula/commit/4061b00c81a5d64e7cd77f588035bc592023e060))
* **renovate:** use org's default preset ([ef5b642](https://github.com/dafyddj/tmp-test-template-formula/commit/ef5b642c0129a24b80ba4a28661180ee2fe16821))
* **semantic-release:** config option no longer works ([b8c7f56](https://github.com/dafyddj/tmp-test-template-formula/commit/b8c7f566fa605506eb684139de1947e50c6e354e))
* **semantic-release:** defer to default `branches` values ([dd33d79](https://github.com/dafyddj/tmp-test-template-formula/commit/dd33d79300956927c281ce69cb6708468e7dc22b))
* **semantic-release:** ignore `dependabot` as author ([f4b5319](https://github.com/dafyddj/tmp-test-template-formula/commit/f4b531940a626b64c9e672448c4bc1014f5f759c))
* **semantic-release:** use `m2r` built in to image ([5ffcb68](https://github.com/dafyddj/tmp-test-template-formula/commit/5ffcb684a09a0c97d41fdb11e075f5880d749148))
* switch commit format to `conventional-commits` ([9b85872](https://github.com/dafyddj/tmp-test-template-formula/commit/9b85872c7808ca68f67a5ffadb84a24755793130))
* **travis:** add notifications => zulip [skip ci] ([ac93ad8](https://github.com/dafyddj/tmp-test-template-formula/commit/ac93ad82f143ce9348f841a263df87d717034103))
* **travis:** add quick check that `convert-formula.sh` has worked ([8312063](https://github.com/dafyddj/tmp-test-template-formula/commit/83120632f3a2246ac640155d374634836c34965a))
* **travis:** apply changes from build config validation [skip ci] ([b625245](https://github.com/dafyddj/tmp-test-template-formula/commit/b625245fc62deb6da7cb35de1280ec267718b1cd))
* **travis:** improve recommended matrix usage comment ([b08a0fd](https://github.com/dafyddj/tmp-test-template-formula/commit/b08a0fdd71adcc1aec742e6199c84942e9cdddfe))
* **travis:** include `commitlint` stage ([6659a69](https://github.com/dafyddj/tmp-test-template-formula/commit/6659a695d1d3606236d14f12b52bf4f0f85e29e3))
* **travis:** opt-in to `dpl v2` to complete build config validation [skip ci] ([f1fbf7f](https://github.com/dafyddj/tmp-test-template-formula/commit/f1fbf7f620c886827c70fb3970e3b2fac58b8db8))
* **travis:** prevent `release` stage running for PRs ([3a072c7](https://github.com/dafyddj/tmp-test-template-formula/commit/3a072c70077ba8b12c12abe4d0640a8a508fe3ab))
* **travis:** quote `${INSTANCE}` when running `kitchen verify` ([00d56a4](https://github.com/dafyddj/tmp-test-template-formula/commit/00d56a4dfcacb6836790e024a024946d23efcf21))
* **travis:** quote pathspecs used with `git ls-files` [skip ci] ([341f495](https://github.com/dafyddj/tmp-test-template-formula/commit/341f495336da0e35d92b3b4acda30f9efa44ec52))
* **travis:** reduce matrix down to 6 instances (ref: [#118](https://github.com/dafyddj/tmp-test-template-formula/issues/118)) ([a8834e2](https://github.com/dafyddj/tmp-test-template-formula/commit/a8834e22da134fddb0063e789d12254c8723a96e))
* **travis:** remove obsolete `markdown-toc` process ([97fbb60](https://github.com/dafyddj/tmp-test-template-formula/commit/97fbb601e9134b953fd9d6b23c20354241f5bd1c))
* **travis:** remove obsolete check based on `$TRAVIS_TEST_RESULT` ([6df9c95](https://github.com/dafyddj/tmp-test-template-formula/commit/6df9c9524c483abb9cf0e0ea028be5286896a923))
* **travis:** remove unavailable files from `markdown-toc` process ([3148f0d](https://github.com/dafyddj/tmp-test-template-formula/commit/3148f0de0861bd25626c72d2540920767b0f41f0))
* **travis:** run `rubocop` during the `Lint` job ([8d8c766](https://github.com/dafyddj/tmp-test-template-formula/commit/8d8c7666602742028c0b2999d683d83d30bb97d9))
* **travis:** run `salt-lint` during the `Lint` job ([2df4646](https://github.com/dafyddj/tmp-test-template-formula/commit/2df46466f6ed5900c0a70d877cd7afc7d484cf13))
* **travis:** run `shellcheck` during lint job ([a711665](https://github.com/dafyddj/tmp-test-template-formula/commit/a7116654d875ecb0e7e3e10fc96cbab2e91575f7))
* **travis:** run linters using `pre-commit` ([6da26cc](https://github.com/dafyddj/tmp-test-template-formula/commit/6da26cca6a3b3ac89137d81b837633358c534396))
* **travis:** update `salt-lint` config for `v0.0.10` [skip ci] ([faea464](https://github.com/dafyddj/tmp-test-template-formula/commit/faea464f923f552e23a83f28e3192c437f7eabfe))
* **travis:** use `env` and `name` for improved display in Travis ([5f773d1](https://github.com/dafyddj/tmp-test-template-formula/commit/5f773d1a5bad9e81521bfd5546e6cc3776c8d451))
* **travis:** use `major.minor` for `semantic-release` version [skip ci] ([e9bfb71](https://github.com/dafyddj/tmp-test-template-formula/commit/e9bfb71fdc0fa80ac63e6ce724f0e5621a4b30ca))
* **travis:** use build config validation (beta) [skip ci] ([66494bb](https://github.com/dafyddj/tmp-test-template-formula/commit/66494bbc1058adc9ed6fa0074b1c4b6018c4cd48))
* update `ci-commitlint` to v1.1.76 ([6cf5ef9](https://github.com/dafyddj/tmp-test-template-formula/commit/6cf5ef9957f87a03bb4a4de4315e81fb712d923e))
* update `ci-docker-python-ruby` to v2.2.45 ([78f551d](https://github.com/dafyddj/tmp-test-template-formula/commit/78f551d6392160eeff181fc9e8c4aa53b2fca66d))
* update `ci-pre-commit` to v2.4.10 ([f266a50](https://github.com/dafyddj/tmp-test-template-formula/commit/f266a5065b93296b7e5c125a5991f381ed1a36f5))
* update `ci-pre-commit` to v2.4.10 ([28d90f5](https://github.com/dafyddj/tmp-test-template-formula/commit/28d90f506f5aae1d849f7324519ab5c74464126b))
* update `ci-pre-commit` to v2.4.10 ([20de9ca](https://github.com/dafyddj/tmp-test-template-formula/commit/20de9ca6386e5b8ce76dffd40978d935f9c0dc3b))
* update `pre-commit` configuration inc. for pre-commit.ci [skip ci] ([32518b9](https://github.com/dafyddj/tmp-test-template-formula/commit/32518b9798ae537f9448214126fb1bc11f2a0ac7))
* update container images ([963522f](https://github.com/dafyddj/tmp-test-template-formula/commit/963522f342f34c30b3f222642eca71da73bdcc32))
* update images for v3006.11 ([a9c769a](https://github.com/dafyddj/tmp-test-template-formula/commit/a9c769ae170f8262e35def4d2bda5afc087eca18))
* update images for v3006.12 & v3007.4 ([52f7dae](https://github.com/dafyddj/tmp-test-template-formula/commit/52f7dae788ba58ab1be76f04e2749548a392c2f0))
* update images for v3006.13 & v3007.5 ([bb45825](https://github.com/dafyddj/tmp-test-template-formula/commit/bb458255f945286e429a671be422975e3d4b1017))
* update images for v3006.14 & v3007.6 ([10aecef](https://github.com/dafyddj/tmp-test-template-formula/commit/10aecefa7fbbe71a96054d5ff147697ecfd7e0d8))
* update images for v3007.2 ([0741129](https://github.com/dafyddj/tmp-test-template-formula/commit/0741129b2d11ce8d02a4f13cfab857b7c2cd3e5d))
* update images for v3007.3 ([747c337](https://github.com/dafyddj/tmp-test-template-formula/commit/747c3370afec0e0600c3f7b7981705356c6f15ae))
* update linters to latest versions [skip ci] ([a284a56](https://github.com/dafyddj/tmp-test-template-formula/commit/a284a566b4284966c7bbbc9da7ad182083a60796))
* update the container images and refactor steps ([b84343e](https://github.com/dafyddj/tmp-test-template-formula/commit/b84343ef831832c7b02326506d2398ef1d6fb67c))
* use `dist: bionic` & apply `opensuse-leap-15` SCP error workaround ([330b0cb](https://github.com/dafyddj/tmp-test-template-formula/commit/330b0cba3a9ae7195c6e4a2c412c39161c64a5bf))
* use latest test images ([417ca53](https://github.com/dafyddj/tmp-test-template-formula/commit/417ca530dd961d47af6ed2132fddbca835989e6d))
* use latest test images ([5fb252c](https://github.com/dafyddj/tmp-test-template-formula/commit/5fb252c0340146cbacdb339cb1a5556f0f85aa8a))
* use latest test images ([b41b8dc](https://github.com/dafyddj/tmp-test-template-formula/commit/b41b8dc94bfdb658a881a6f7bded22e912bbb323))
* use latest test images ([579a43b](https://github.com/dafyddj/tmp-test-template-formula/commit/579a43b7a9c80ccb3bad179c61ee2af50ac139bb))
* use latest test images ([b71ff75](https://github.com/dafyddj/tmp-test-template-formula/commit/b71ff7523ae70b8501479ca943b885a1c283bf38))
* use latest test images ([d53ceae](https://github.com/dafyddj/tmp-test-template-formula/commit/d53ceae71bfb149e766f0bde28a20a469f2ab5f3))
* use upstream `maintainer` with new `ignore` option ([bb9320c](https://github.com/dafyddj/tmp-test-template-formula/commit/bb9320c2ad3caa3cba8442bf261fb09e161c93c2))
* **workflows/commitlint:** add to repo [skip ci] ([574d18f](https://github.com/dafyddj/tmp-test-template-formula/commit/574d18fc2c9628ed142a380aaff3b4c31592bb6f))
* **workflows:** add new `main` workflow running `pre-commit` ([5bc2f5d](https://github.com/dafyddj/tmp-test-template-formula/commit/5bc2f5da1d4cda245aff13180906bdd88e37e700))
* **workflows:** add testing for some platforms to GitHub Actions ([7eb8b73](https://github.com/dafyddj/tmp-test-template-formula/commit/7eb8b737ce52ecf4e1ad0977732b53d81a28dbe7))
* **workflows:** checkout treeless clone w/ history/tags for `commitlint` ([e128c82](https://github.com/dafyddj/tmp-test-template-formula/commit/e128c8203fa949c198e2cb362f38f891e224d9db))
* **workflows:** exception for `line-length` ([f6eb9cf](https://github.com/dafyddj/tmp-test-template-formula/commit/f6eb9cf0cf8a582e08e98a2ade35c26ca4269bb6))
* **workflows:** improve `pre-commit` caching ([38d87fc](https://github.com/dafyddj/tmp-test-template-formula/commit/38d87fc4d19da0c1c431d25b8bf4680e13f287be))
* **workflows:** increase `pre-commit` timeout to 10 minutes ([3f23281](https://github.com/dafyddj/tmp-test-template-formula/commit/3f232813a3a9d300359d296ff4480991f9bed24b))
* **workflows:** remove trailing comma ([5039aba](https://github.com/dafyddj/tmp-test-template-formula/commit/5039aba8fb809d427c31091b7b7e189190234b83))
* **yamllint:** add rule `empty-values` & use new `yaml-files` setting ([70ed7e2](https://github.com/dafyddj/tmp-test-template-formula/commit/70ed7e2f108a35df39106d765931b603951d6894)), closes [#164](https://github.com/dafyddj/tmp-test-template-formula/issues/164)

### Maintenance

* **`libsaltcli`:** add lib to check type of Salt command being used ([a6487b5](https://github.com/dafyddj/tmp-test-template-formula/commit/a6487b5cf9cf2736d1e5f386be4b418d7bc2461b)), closes [#102](https://github.com/dafyddj/tmp-test-template-formula/issues/102) [#114](https://github.com/dafyddj/tmp-test-template-formula/issues/114) [#115](https://github.com/dafyddj/tmp-test-template-formula/issues/115) [#186](https://github.com/dafyddj/tmp-test-template-formula/issues/186)
* **codeowners:** add to repo [skip ci] ([9672880](https://github.com/dafyddj/tmp-test-template-formula/commit/9672880fd06e5b434c5df293f908e1b8e2347527))
* **codeowners:** update `semantic-release` related files [skip ci] ([86c3ff7](https://github.com/dafyddj/tmp-test-template-formula/commit/86c3ff7edbc7c934ef5f2867ad2b2280ca6c0ccf))
* **convert-formula:** add `.gitlab-ci.yml` to pattern deletion section ([7f4c12a](https://github.com/dafyddj/tmp-test-template-formula/commit/7f4c12a82cd09577b195e86d335a1e0e375e896a))
* **deps:** bump `addressable` from `2.7.0` to `2.8.0` [skip ci] ([c8ca950](https://github.com/dafyddj/tmp-test-template-formula/commit/c8ca950d8e464f400cfc1a2fcd172f88811c9293))
* **deps:** bump nokogiri from 1.18.8 to 1.18.9 ([1c4d414](https://github.com/dafyddj/tmp-test-template-formula/commit/1c4d4146eafcf45d7ad51f305c3c7f83d3ad734d))
* **deps:** bump thor from 1.3.2 to 1.4.0 ([1037059](https://github.com/dafyddj/tmp-test-template-formula/commit/1037059d8c7a140bd40f0f958d6fad199c4eede2))
* **deps:** pin dependencies ([a352cce](https://github.com/dafyddj/tmp-test-template-formula/commit/a352cce0aa6883f57ea976a48f8c4f914c0d6fc0))
* **deps:** pin dependencies ([ecd792f](https://github.com/dafyddj/tmp-test-template-formula/commit/ecd792f09db3dd7e037805cd7cc3ba553321caaf))
* **deps:** pin dependencies ([8f88f78](https://github.com/dafyddj/tmp-test-template-formula/commit/8f88f78471dc4c28c2b1feea5c1c365c92d3f452))
* **deps:** update `github-actions` non-major actions/images ([84007ec](https://github.com/dafyddj/tmp-test-template-formula/commit/84007ec50512e1dba6f53ba5635233de77ad1928))
* **deps:** update `github-actions` non-major actions/images ([df4b97c](https://github.com/dafyddj/tmp-test-template-formula/commit/df4b97cd34a5639fae1fa84abfb1cbbe2f5c293d))
* **deps:** update `github-actions` non-major actions/images ([ea6d6f8](https://github.com/dafyddj/tmp-test-template-formula/commit/ea6d6f809654bf7bc0901fcfbe70bbab55df6766))
* **deps:** update `github-actions` non-major actions/images ([c20101d](https://github.com/dafyddj/tmp-test-template-formula/commit/c20101d904bb944854025d2d1ed4cda3122234ed))
* **deps:** update `github-actions` non-major actions/images ([b2a5c17](https://github.com/dafyddj/tmp-test-template-formula/commit/b2a5c174229713863931953d1d51e9d42e33f69e))
* **deps:** update `github-actions` non-major actions/images ([b732abb](https://github.com/dafyddj/tmp-test-template-formula/commit/b732abbfdd990acfe0643b64af81339a83b985ce))
* **deps:** update `github-actions` non-major actions/images ([3303200](https://github.com/dafyddj/tmp-test-template-formula/commit/3303200bb97e262a8ccf0766635525f9ffed7766))
* **deps:** update `gitlabci` non-major images ([b13f922](https://github.com/dafyddj/tmp-test-template-formula/commit/b13f922f1a42e8d22f01c75dd7f6c6ecc081ed02))
* **deps:** update `gitlabci` non-major images ([9f47d72](https://github.com/dafyddj/tmp-test-template-formula/commit/9f47d72515945df9d58bee9743ca9f5587d3c9f6))
* **deps:** update `gitlabci` non-major images ([87209c4](https://github.com/dafyddj/tmp-test-template-formula/commit/87209c4e4d8323ad3eb163f754d645eccd57378a))
* **deps:** update `gitlabci` non-major images ([5192944](https://github.com/dafyddj/tmp-test-template-formula/commit/5192944383773adb6e6656cd68e396535fc76cb6))
* **deps:** update `gitlabci` non-major images ([bd35cc1](https://github.com/dafyddj/tmp-test-template-formula/commit/bd35cc1d1c86918d8ac17ff02e8842bd360538af))
* **deps:** update `gitlabci` non-major images ([de5ee07](https://github.com/dafyddj/tmp-test-template-formula/commit/de5ee07e773b623cc7d8b5ac621ffcf98f64c28c))
* **deps:** update `gitlabci` non-major images ([a440ee7](https://github.com/dafyddj/tmp-test-template-formula/commit/a440ee70447ddefb80ced13525736c6a41f3170d))
* **deps:** update `gitlabci` non-major images ([3336e67](https://github.com/dafyddj/tmp-test-template-formula/commit/3336e671d8a2945ab949c10bc2f7994b165fa5e8))
* **deps:** update `gitlabci` non-major images ([31afee2](https://github.com/dafyddj/tmp-test-template-formula/commit/31afee2742714484c83db49ee86cf9f0caff59ae))
* **deps:** update `gitlabci` non-major images ([b060d4f](https://github.com/dafyddj/tmp-test-template-formula/commit/b060d4f9c336519940b71d6edd3784cd221d3916))
* **deps:** update `gitlabci` non-major images ([b9b9a7e](https://github.com/dafyddj/tmp-test-template-formula/commit/b9b9a7ed0cd90cb2d25433159e2d7433ab36fd23))
* **deps:** update `pre-commit` non-major hooks ([76fbc56](https://github.com/dafyddj/tmp-test-template-formula/commit/76fbc56e8bd39a2919c11cb22fc13dc7c7a41407))
* **deps:** update `pre-commit` non-major hooks ([36420ef](https://github.com/dafyddj/tmp-test-template-formula/commit/36420ef14956d5c248417dec9b5ad22ff1c86b63))
* **deps:** update `pre-commit` non-major hooks ([ac35477](https://github.com/dafyddj/tmp-test-template-formula/commit/ac35477ddf72ee28e0e6d01dbd95a4a142a7c0c4))
* **deps:** update `pre-commit` non-major hooks ([dbda1f2](https://github.com/dafyddj/tmp-test-template-formula/commit/dbda1f2219ff827e9026dffc94defcaf71271ad9))
* **deps:** update `pre-commit` non-major hooks ([62992e1](https://github.com/dafyddj/tmp-test-template-formula/commit/62992e152696428159a70f63d9cd178c2e286e0f))
* **deps:** update `pre-commit` non-major hooks ([5396061](https://github.com/dafyddj/tmp-test-template-formula/commit/5396061bf40095edee7a1941a79eba917dcfe8a1))
* **deps:** update actions/checkout action to v5 ([8f43acc](https://github.com/dafyddj/tmp-test-template-formula/commit/8f43acc813597d120e08bf96591a46b2324270ac))
* **deps:** update gitlab ci docker non-major images ([13dc5b2](https://github.com/dafyddj/tmp-test-template-formula/commit/13dc5b2e5bdfa6bc3fc481be04787ff6686e706c))
* **deps:** update gitlab ci docker non-major images ([2b9b0f9](https://github.com/dafyddj/tmp-test-template-formula/commit/2b9b0f9ac59dc7facc90297a46e7583bd0f22f85))
* **deps:** update gitlab ci docker non-major images ([041b00e](https://github.com/dafyddj/tmp-test-template-formula/commit/041b00eae954e50fc1b9f7f51a33301db53b5b5e))
* **deps:** update gitlab ci docker non-major images ([5a68834](https://github.com/dafyddj/tmp-test-template-formula/commit/5a68834dc205667d3cc88a6fcd9265d2542d4eb3))
* **deps:** update gitlab ci docker non-major images ([f3f1b5f](https://github.com/dafyddj/tmp-test-template-formula/commit/f3f1b5ff8c591fdd2b2d7a684ce1e727eacb029f))
* **deps:** update pre-commit hook minor/patch ([f82fc41](https://github.com/dafyddj/tmp-test-template-formula/commit/f82fc41dd290a16c5723448b358e2361cf4fb522))
* **deps:** update pre-commit hook minor/patch ([b27d669](https://github.com/dafyddj/tmp-test-template-formula/commit/b27d669813f9fe776fd98e0d198e70e8f5c10ad0))
* **deps:** update pre-commit hook pre-commit/pre-commit-hooks to v6 ([bea27a8](https://github.com/dafyddj/tmp-test-template-formula/commit/bea27a8ab472c57eebaf621a99baee237fe70150))
* **deps:** update pre-commit hook renovatebot/pre-commit-hooks to v41 ([3a32abd](https://github.com/dafyddj/tmp-test-template-formula/commit/3a32abd2aabb80d61ce6af2388ec28b2c7ca772e))
* **deps:** update pre-commit hook renovatebot/pre-commit-hooks to v41.42.2 ([7f4d754](https://github.com/dafyddj/tmp-test-template-formula/commit/7f4d754933551b0d7426d5cb529e9173220a30b0))
* **deps:** update pre-commit hook renovatebot/pre-commit-hooks to v41.63.0 ([88a6219](https://github.com/dafyddj/tmp-test-template-formula/commit/88a62196e88452ebc2eb438b6597757db56bb449))
* **deps:** update pre-commit hook rubocop-hq/rubocop to v1.79.2 ([099abfb](https://github.com/dafyddj/tmp-test-template-formula/commit/099abfb6a002c3c1a7702dee6072c068f02c37eb))
* **deps:** update pre-commit non-major hooks ([74f8d95](https://github.com/dafyddj/tmp-test-template-formula/commit/74f8d9572192e97135c59fdf51bdfa9320f7ebad))
* **deps:** update pre-commit non-major hooks ([2ac42fd](https://github.com/dafyddj/tmp-test-template-formula/commit/2ac42fd92931a31b47d1766f048ec0c9836275fe))
* **deps:** update pre-commit non-major hooks ([f7757a6](https://github.com/dafyddj/tmp-test-template-formula/commit/f7757a615705e4edd7787d663711955fd080054f))
* **deps:** update techneg/ci-commitlint docker tag to v1.1.86 ([9b9b000](https://github.com/dafyddj/tmp-test-template-formula/commit/9b9b0001bce25fb3cfeb74c40395ada990f2293e))
* **deps:** update techneg/ci-docker-python-ruby docker tag to v2.2.55 ([3ad1fb3](https://github.com/dafyddj/tmp-test-template-formula/commit/3ad1fb3cfcda99c1db1d914a957094ee2375a5b9))
* **deps:** update techneg/ci-pre-commit docker tag to v2.4.20 ([6a57f17](https://github.com/dafyddj/tmp-test-template-formula/commit/6a57f17ed3ec781ed0a7d8b84c795292eec16b0c))
* **deps:** update techneg/ci-pre-commit docker tag to v2.4.27 ([3b3d10d](https://github.com/dafyddj/tmp-test-template-formula/commit/3b3d10db244b1ad291e992ae6ca94b6b992c3f94))
* **deps:** update techneg/ci-pre-commit docker tag to v2.4.28 ([b895f81](https://github.com/dafyddj/tmp-test-template-formula/commit/b895f81481e3c7c1d08bb27ab1fa6f16b09d8e02))
* **deps:** update techneg/ci-pre-commit docker tag to v2.4.29 ([a5e1ef7](https://github.com/dafyddj/tmp-test-template-formula/commit/a5e1ef72317c2eb84533c5b97b9356380276ee54))
* **deps:** update techneg/ci-pre-commit docker tag to v2.4.30 ([f75c4c4](https://github.com/dafyddj/tmp-test-template-formula/commit/f75c4c4368da7925179b2b0164a1fbae39e13dc5))
* exclude `coqbot` commits from linting ([c7e3955](https://github.com/dafyddj/tmp-test-template-formula/commit/c7e3955a97ff902abe86683a6caa84baa68cd07c))
* exclude Copier and `pre-commit.ci` commits from linting ([c0ac6d9](https://github.com/dafyddj/tmp-test-template-formula/commit/c0ac6d9df7cd7c02aae4de204f763fb61e89cd50))
* exclude Renovate commits from linting ([69f2b96](https://github.com/dafyddj/tmp-test-template-formula/commit/69f2b96ef8f49e1b99ffb6e8f72c3422252271c8))
* **gemfile.lock:** update to latest gem versions (2020-W25) [skip ci] ([44e29ce](https://github.com/dafyddj/tmp-test-template-formula/commit/44e29ce5c5d449cdb683ca2effab616196c06d64))
* **gemfile.lock:** update to latest gem versions (2020-W26) [skip ci] ([b3a3f04](https://github.com/dafyddj/tmp-test-template-formula/commit/b3a3f04d094964cfc1f754f8ad0378644fee923e))
* **gemfile.lock:** update to latest gem versions (2020-W27) [skip ci] ([3ade717](https://github.com/dafyddj/tmp-test-template-formula/commit/3ade71739cb2146c99a549fa5fde6d029dd20e9c))
* **gemfile.lock:** update to latest gem versions (2021-W29) [skip ci] ([9ef82f4](https://github.com/dafyddj/tmp-test-template-formula/commit/9ef82f4f7857c7837192c7d7a8ac473c94831693))
* **gemfile.lock:** update to latest gem versions (2021-W30) [skip ci] ([305765a](https://github.com/dafyddj/tmp-test-template-formula/commit/305765af93bf25b1d0dc2fcb64ae5d81bde00973))
* **gemfile.lock:** update to latest gem versions (2021-W31) [skip ci] ([f6357aa](https://github.com/dafyddj/tmp-test-template-formula/commit/f6357aad437b4b0ba1c4ebe3e851eb22427d4655))
* **gemfile.lock:** update to latest gem versions (2021-W32) [skip ci] ([84cb63f](https://github.com/dafyddj/tmp-test-template-formula/commit/84cb63fc8e14a7071d66025212d44299d691c37b))
* **gemfile.lock:** update to latest gem versions (2021-W33) [skip ci] ([b4b0385](https://github.com/dafyddj/tmp-test-template-formula/commit/b4b03854d68286c667c8b9d10f32ec87bb743dc8))
* **gemfile.lock:** update to latest gem versions (2021-W34) [skip ci] ([8d506ea](https://github.com/dafyddj/tmp-test-template-formula/commit/8d506ea93eca196c60e178f8dd2eb2a7ad6594e9))
* **gemfile.lock:** update to latest gem versions (2021-W35) [skip ci] ([24219b6](https://github.com/dafyddj/tmp-test-template-formula/commit/24219b68d13857571e8e008e7183d1f9a89ed10d))
* **gemfile.lock:** update to latest gem versions (2021-W36) [skip ci] ([855fc38](https://github.com/dafyddj/tmp-test-template-formula/commit/855fc387505fdfbd7698bbf96a06663f85e838bc))
* **gemfile.lock:** update to latest gem versions (2021-W37) [skip ci] ([81ae627](https://github.com/dafyddj/tmp-test-template-formula/commit/81ae6276f5cbbf3458defa2be6131f0af910a456))
* **gemfile.lock:** update to latest gem versions (2021-W38) [skip ci] ([7bacfb3](https://github.com/dafyddj/tmp-test-template-formula/commit/7bacfb34b418fb89ccc561125273a738abf864e8))
* **gemfile.lock:** update to latest gem versions (2021-W39) [skip ci] ([e7a45f4](https://github.com/dafyddj/tmp-test-template-formula/commit/e7a45f4ac86ab2eee01ec02843f164afe51e99c3))
* **gemfile.lock:** update to latest gem versions (2021-W40) [skip ci] ([2d6c666](https://github.com/dafyddj/tmp-test-template-formula/commit/2d6c666c7041bfe87f9af6d1926eb06da889fa33))
* **gemfile.lock:** update to latest gem versions (2021-W41) [skip ci] ([5ebc802](https://github.com/dafyddj/tmp-test-template-formula/commit/5ebc802f1397ade83467c79703e5c1b3d5cd1ffc))
* **gemfile.lock:** update to latest gem versions (2021-W42) [skip ci] ([37c6181](https://github.com/dafyddj/tmp-test-template-formula/commit/37c618176de1f44056e2b58c0007b77350d0aa5f))
* **gemfile.lock:** update to latest gem versions (2021-W43) [skip ci] ([4d8b35a](https://github.com/dafyddj/tmp-test-template-formula/commit/4d8b35ace1a023f39a139245c51f4f29cacacca1))
* **gemfile.lock:** update to latest gem versions (2021-W47) [skip ci] ([db31b94](https://github.com/dafyddj/tmp-test-template-formula/commit/db31b94993225849ff64230a00ea0f028b5d7c91))
* **gemfile.lock:** update to latest gem versions (2021-W49) [skip ci] ([7ea1b92](https://github.com/dafyddj/tmp-test-template-formula/commit/7ea1b9252074cd99d89d298d6aa5ac5e8eba2edc))
* **gemfile.lock:** update to latest gem versions (2021-W50) [skip ci] ([42b2c19](https://github.com/dafyddj/tmp-test-template-formula/commit/42b2c199c1b8c303458c16f0cce6396bfa970608))
* **gemfile.lock:** update to latest gem versions (2021-W51) [skip ci] ([bf1e46e](https://github.com/dafyddj/tmp-test-template-formula/commit/bf1e46e69bf8b190b4f5e35a2322c9d00870fdc9))
* **gemfile.lock:** update to latest gem versions (2021-W52) [skip ci] ([bcfc217](https://github.com/dafyddj/tmp-test-template-formula/commit/bcfc217f429baeb07864cc6690dc1272fca6df2f))
* **gemfile.lock:** update to latest gem versions (2022-W01) [skip ci] ([b85855a](https://github.com/dafyddj/tmp-test-template-formula/commit/b85855a769ba70a4f2e90a6c792bf5278e9c7953))
* **gemfile.lock:** update to latest gem versions (2022-W02) [skip ci] ([8d07352](https://github.com/dafyddj/tmp-test-template-formula/commit/8d073523aae5bf64c7c6b2d265cdcb8b2dd7451b))
* **gemfile.lock:** update to latest gem versions (2022-W03) [skip ci] ([d8dc1fe](https://github.com/dafyddj/tmp-test-template-formula/commit/d8dc1fe4572cfe37f5856d2db429d7e88953c1a2))
* **gemfile.lock:** update to latest gem versions (2022-W04) [skip ci] ([a5bcbc4](https://github.com/dafyddj/tmp-test-template-formula/commit/a5bcbc4be5a7e4fa82664b189b595719455f90ea))
* **gemfile.lock:** update to latest gem versions (2022-W05) [skip ci] ([cb6fb33](https://github.com/dafyddj/tmp-test-template-formula/commit/cb6fb337b8e276af3041ed32cbcf8a7b5a8f4f89))
* **gemfile.lock:** update to latest gem versions (2022-W06) [skip ci] ([4710235](https://github.com/dafyddj/tmp-test-template-formula/commit/4710235ac51291fe209b4d615dff59be36b6b327))
* **gemfile.lock:** update to latest gem versions (2022-W07) [skip ci] ([080fdcd](https://github.com/dafyddj/tmp-test-template-formula/commit/080fdcd9f136f19d2a7dd15b17bf4de5c1c4a3c8))
* **gemfile.lock:** update to latest gem versions (2022-W08) [skip ci] ([278404f](https://github.com/dafyddj/tmp-test-template-formula/commit/278404f7717721b00103db62edfaf5aa671a9904))
* **gemfile.lock:** update to latest gem versions (2022-W09) [skip ci] ([a8c8f81](https://github.com/dafyddj/tmp-test-template-formula/commit/a8c8f81952e5b59462c4ea80e01422d745ed88ff))
* **gemfile.lock:** update to latest gem versions (2022-W10) [skip ci] ([6b04b95](https://github.com/dafyddj/tmp-test-template-formula/commit/6b04b953a3c7a47b492a2036348a78b56ddcf3a0))
* **gemfile.lock:** update to latest gem versions (2022-W11) [skip ci] ([5ce256d](https://github.com/dafyddj/tmp-test-template-formula/commit/5ce256d56aac25a67891985db4f97329a70bffc6))
* **gemfile.lock:** update to latest gem versions (2022-W12) [skip ci] ([409bfc5](https://github.com/dafyddj/tmp-test-template-formula/commit/409bfc5f5764a9942d9fc74c0e07612142ca864b))
* **gemfile.lock:** update to latest gem versions (2022-W13) [skip ci] ([bbc8e2d](https://github.com/dafyddj/tmp-test-template-formula/commit/bbc8e2d851bf27fe38df2493a57e22a43b47988e))
* **gemfile.lock:** update to latest gem versions (2022-W14) [skip ci] ([2dcea70](https://github.com/dafyddj/tmp-test-template-formula/commit/2dcea70d8955332e8e01bf05ae3d25be55799906))
* **gemfile.lock:** update to latest gem versions (2022-W15) [skip ci] ([7d256e3](https://github.com/dafyddj/tmp-test-template-formula/commit/7d256e32f8326c5963d21339587f4aae3b038217))
* **gemfile.lock:** update to latest gem versions (2022-W16) [skip ci] ([6be1e23](https://github.com/dafyddj/tmp-test-template-formula/commit/6be1e23bc758f8b20f35444df42dfb974c1d0db4))
* **gemfile.lock:** update to latest gem versions (2022-W17) [skip ci] ([876385a](https://github.com/dafyddj/tmp-test-template-formula/commit/876385a1369f534d8d789d5b111a1b6d69d15685))
* **gemfile.lock:** update to latest gem versions (2022-W18) [skip ci] ([e16130d](https://github.com/dafyddj/tmp-test-template-formula/commit/e16130d239d0d99d1fed20ab478b1894be20e267))
* **gemfile.lock:** update to latest gem versions (2022-W19) [skip ci] ([1703b38](https://github.com/dafyddj/tmp-test-template-formula/commit/1703b38c8e99e87ff1f3dd8ae511b6de4c1164ad))
* **gemfile.lock:** update to latest gem versions (2022-W20) [skip ci] ([de7e21c](https://github.com/dafyddj/tmp-test-template-formula/commit/de7e21c762dbf5bf0722c33193eb59eb2f5e8ee6))
* **gemfile.lock:** update to latest gem versions (2022-W22) [skip ci] ([c090f3d](https://github.com/dafyddj/tmp-test-template-formula/commit/c090f3d0810a21f1caa476f90a7f2dc683d3f8da))
* **gemfile.lock:** update to latest gem versions (2022-W23) [skip ci] ([2e2aa10](https://github.com/dafyddj/tmp-test-template-formula/commit/2e2aa10e5d5d84d68a7db4eea61dbb83baa21253))
* **gemfile.lock:** update to latest gem versions (2022-W24) [skip ci] ([5e5aa74](https://github.com/dafyddj/tmp-test-template-formula/commit/5e5aa74c6629be9ae1916b0e4e1ba8fef2dc8279))
* **gemfile.lock:** update to latest gem versions (2022-W26) [skip ci] ([e7fc7eb](https://github.com/dafyddj/tmp-test-template-formula/commit/e7fc7eb295ad1833cf964b8b17386ba67f26fafd))
* **gemfile.lock:** update to latest gem versions (2022-W28) [skip ci] ([fc04282](https://github.com/dafyddj/tmp-test-template-formula/commit/fc04282106ef41d47a74b81c09bfc9f9852db94a))
* **gemfile.lock:** update to latest gem versions (2023-W42) ([20bf1d5](https://github.com/dafyddj/tmp-test-template-formula/commit/20bf1d5a17ce28fbf575780b2631701d70b7684f))
* **gemfile.lock:** update to latest gem versions [skip ci] ([040125d](https://github.com/dafyddj/tmp-test-template-formula/commit/040125dfafca9be3eac8159c3ff9d434ef0a971f))
* **gemfile.lock:** update to latest gem versions [skip ci] ([2f3ed32](https://github.com/dafyddj/tmp-test-template-formula/commit/2f3ed3259fec1763eb59114936dd594a1ce0bcd8))
* **gemfile.lock:** update to latest gem versions [skip ci] ([b433f3e](https://github.com/dafyddj/tmp-test-template-formula/commit/b433f3eb9fc40c040a845e466b371ac4d04bce30))
* **gemfile+lock:** pin versions of key dependencies ([e833927](https://github.com/dafyddj/tmp-test-template-formula/commit/e833927250ccfd3ae6b00b0a7158609a43142806))
* **gemfile+lock:** update in line with Chef WS v25.5.1084 ([830b921](https://github.com/dafyddj/tmp-test-template-formula/commit/830b9212908838b7ea56c4edb53e5b0fd949ff00))
* **gemfile+lock:** update to latest gem versions (2020-W41) [skip ci] ([46e6821](https://github.com/dafyddj/tmp-test-template-formula/commit/46e68213a1203d1d28217481f1b1746fdd43b555))
* **gemfile+lock:** update to latest gem versions (2020-W43) [skip ci] ([d3fdd36](https://github.com/dafyddj/tmp-test-template-formula/commit/d3fdd361994609e2e725a619a9ac96b004bc7786))
* **gemfile+lock:** update to latest gem versions (2020-W44) [skip ci] ([ef7330d](https://github.com/dafyddj/tmp-test-template-formula/commit/ef7330d48526f0e254d6930c8ee3220620ee4a5e))
* **gemfile+lock:** update to latest gem versions (2021-W28) [skip ci] ([a04fba1](https://github.com/dafyddj/tmp-test-template-formula/commit/a04fba14ec55777c3eb300fdd154fca8b086862c))
* **git:** add Bundler config dir to `.gitignore` ([12d059b](https://github.com/dafyddj/tmp-test-template-formula/commit/12d059bd384c5df57250b59820b6f46f8c3a4c38))
* **git:** add visual studio to gitignore ([53b7666](https://github.com/dafyddj/tmp-test-template-formula/commit/53b7666c33a73bb7b7ca82d04c74b4fb6037f7a4))
* **gitignore:** add `kitchen.local.yml` ([fe9eae0](https://github.com/dafyddj/tmp-test-template-formula/commit/fe9eae0841f109d58e5a3df7a2c7f104b41e51c3))
* **issues:** remove issues templates to use org-level templates [skip ci] ([627bca0](https://github.com/dafyddj/tmp-test-template-formula/commit/627bca05f48afcb4524cbcefe5cea0893e5d2381))
* **pre-commit:** add utility script to install hooks and environments ([01fd4e6](https://github.com/dafyddj/tmp-test-template-formula/commit/01fd4e65f44284357cdb06bc9a8a027887933deb))
* **pre-commit:** check commit message using `commitlint` ([5cdefdc](https://github.com/dafyddj/tmp-test-template-formula/commit/5cdefdc6a5993addcc73090831e821460735e4c3))
* **pre-commit:** check reST files using `rstcheck` ([a1d53a9](https://github.com/dafyddj/tmp-test-template-formula/commit/a1d53a975882746fac27041f30092d6ce5cb7a77))
* **pre-commit:** check Ruby files using `rubocop` ([5bccc81](https://github.com/dafyddj/tmp-test-template-formula/commit/5bccc810bafb666bc098255ddbff8017244c17f7))
* **pre-commit:** check Salt files using `salt-lint` ([7011762](https://github.com/dafyddj/tmp-test-template-formula/commit/70117620d7c279d21d00d960593914af0d7e2b52))
* **pre-commit:** check shell files using `shellcheck` ([c50c081](https://github.com/dafyddj/tmp-test-template-formula/commit/c50c0810696d04fcc4709b80f5796de04fd811c0))
* **pre-commit:** check YAML files using `yamllint` ([3f26ea7](https://github.com/dafyddj/tmp-test-template-formula/commit/3f26ea7cd4aedeedc1c78fbe530ac774eb6d7dc9))
* **pre-commit:** use `info` report level for `rstcheck` [skip ci] ([7bbaab5](https://github.com/dafyddj/tmp-test-template-formula/commit/7bbaab5e924432884468e5c7abec82747709b923))
* **release:** 0.3.0 [skip ci] ([b731437](https://github.com/dafyddj/tmp-test-template-formula/commit/b731437de95a2b5baf64bbb873a99b09bc92236b))
* **release:** 0.3.1 [skip ci] ([c8b47d3](https://github.com/dafyddj/tmp-test-template-formula/commit/c8b47d33cdf25d2e5bbf97bd03334f2dcbb10d16))
* **release:** 0.3.2 [skip ci] ([fb0ecb7](https://github.com/dafyddj/tmp-test-template-formula/commit/fb0ecb7c25daccb2799e9f1c79bc8ff7c8643f8b))
* **release:** 0.3.3 [skip ci] ([43bf166](https://github.com/dafyddj/tmp-test-template-formula/commit/43bf1669fbc155968d10920cb0d83741836e82c2))
* **release:** 0.3.4 [skip ci] ([3c7192f](https://github.com/dafyddj/tmp-test-template-formula/commit/3c7192f885b15bd08a78f9c068248f5055e56b63))
* **release:** 0.3.5 [skip ci] ([8fca3a9](https://github.com/dafyddj/tmp-test-template-formula/commit/8fca3a9e321b55d5ec5dac94fe5630a1d97b1c28))
* **release:** 0.3.6 [skip ci] ([fc664e7](https://github.com/dafyddj/tmp-test-template-formula/commit/fc664e731e00e516aadfe0f5fc533d2850fcbb1b))
* **release:** 0.4.0 [skip ci] ([0dc0dc4](https://github.com/dafyddj/tmp-test-template-formula/commit/0dc0dc4b60d103e2ca385146f372b125e345f059))
* **release:** 0.5.0 [skip ci] ([c45ea67](https://github.com/dafyddj/tmp-test-template-formula/commit/c45ea67a0d9e638a1743940222f37fb541923124))
* **release:** 0.6.0 [skip ci] ([69bc840](https://github.com/dafyddj/tmp-test-template-formula/commit/69bc840e223accc1f8d13caff4ff546db42062f0))
* **release:** 0.7.0 [skip ci] ([6bf86d8](https://github.com/dafyddj/tmp-test-template-formula/commit/6bf86d854d76fc2cf9f1cf3018d2207403f1391e))
* **release:** 0.7.1 [skip ci] ([12a3c7b](https://github.com/dafyddj/tmp-test-template-formula/commit/12a3c7b91d5cb1414d006a1ceb41f1703348a23f))
* **release:** 0.7.2 [skip ci] ([0fabb21](https://github.com/dafyddj/tmp-test-template-formula/commit/0fabb21cc804045749ca4c42f3a051761e2b74ae))
* **release:** 0.7.3 [skip ci] ([ed00758](https://github.com/dafyddj/tmp-test-template-formula/commit/ed007581333b3beb900f994f464c5061f16b388c))
* **release:** 0.7.4 [skip ci] ([c71915e](https://github.com/dafyddj/tmp-test-template-formula/commit/c71915ed1e38d72c38360d409ddcffd01a61f557))
* **release:** 0.7.5 [skip ci] ([6d01188](https://github.com/dafyddj/tmp-test-template-formula/commit/6d01188d3e340b6b1365dc2edce8ed8d3f9a57dc))
* **release:** 0.7.6 [skip ci] ([be780db](https://github.com/dafyddj/tmp-test-template-formula/commit/be780db7f26a6e24ae0f5cd0926442f5c3e49de5))
* **release:** 1.0.0 [skip ci] ([b91d304](https://github.com/dafyddj/tmp-test-template-formula/commit/b91d304b93289e57feaf64f591413e87b0ca58d1))
* **release:** 1.0.1 [skip ci] ([eb246a2](https://github.com/dafyddj/tmp-test-template-formula/commit/eb246a284c3221ab5f102c42330ff9e76c319a2a))
* **release:** 1.1.0 [skip ci] ([7abef94](https://github.com/dafyddj/tmp-test-template-formula/commit/7abef942327e7539ecfd1b592cb5ee291f637bd5))
* **release:** 1.1.1 [skip ci] ([ea1841c](https://github.com/dafyddj/tmp-test-template-formula/commit/ea1841c08d376b4e0fa240c212a401b6f3eb505c))
* **release:** 1.1.2 [skip ci] ([1a26fdd](https://github.com/dafyddj/tmp-test-template-formula/commit/1a26fdda069ec2e3b6cc96bdf1402b0d39bf6044))
* **release:** 1.2.0 [skip ci] ([a52523b](https://github.com/dafyddj/tmp-test-template-formula/commit/a52523b9f4601e2331aaac267deaedfcde402242))
* **release:** 1.2.1 [skip ci] ([eab481c](https://github.com/dafyddj/tmp-test-template-formula/commit/eab481cd4ffbc30d790974a58bbf3de7d5a4b3ee))
* **release:** 1.2.2 [skip ci] ([18e5a3d](https://github.com/dafyddj/tmp-test-template-formula/commit/18e5a3dac130eb2d855943194a91e38f97b72acc))
* **release:** 1.2.3 [skip ci] ([193bba8](https://github.com/dafyddj/tmp-test-template-formula/commit/193bba805fc14d3f0f61c71b6ce4bbf45a60312c))
* **release:** 1.2.4 [skip ci] ([6ceb238](https://github.com/dafyddj/tmp-test-template-formula/commit/6ceb238248afb4186ceb7b0659a7ddaeb7656240))
* **release:** 1.2.5 [skip ci] ([66ece76](https://github.com/dafyddj/tmp-test-template-formula/commit/66ece768dd86351be395c9ca2661c9c2a4e65b72))
* **release:** 1.2.6 [skip ci] ([483ce48](https://github.com/dafyddj/tmp-test-template-formula/commit/483ce48ae4d3dd093cce82ef1144efea037712e9))
* **release:** 2.0.0 [skip ci] ([709d6a2](https://github.com/dafyddj/tmp-test-template-formula/commit/709d6a22943514cc7f5f218fd96f7c26bc7f2432))
* **release:** 2.0.1 [skip ci] ([0dab08d](https://github.com/dafyddj/tmp-test-template-formula/commit/0dab08d55389069f98deab7100ca44f5651abd5f))
* **release:** 2.0.2 [skip ci] ([a3ebe2b](https://github.com/dafyddj/tmp-test-template-formula/commit/a3ebe2b26e16d28f53a26fc262e70e0ce53b66f2))
* **release:** 2.0.3 [skip ci] ([34d235a](https://github.com/dafyddj/tmp-test-template-formula/commit/34d235a757e97ad23825606b8eb60b67776692e6))
* **release:** 2.0.4 [skip ci] ([809207e](https://github.com/dafyddj/tmp-test-template-formula/commit/809207e7f246a1a4e427cb4174e07ca26b4ef4ce))
* **release:** 2.0.5 [skip ci] ([3a83a69](https://github.com/dafyddj/tmp-test-template-formula/commit/3a83a691988579985e95aff12eee1b8e62077e0c))
* **release:** 2.0.6 [skip ci] ([b0d6aa1](https://github.com/dafyddj/tmp-test-template-formula/commit/b0d6aa1f8cee0b97ea38a3a368ebfdbea1fff30c))
* **release:** 2.1.0 [skip ci] ([abcb789](https://github.com/dafyddj/tmp-test-template-formula/commit/abcb789063587e81b02a15bb9593a81a0f1d4b98))
* **release:** 2.1.1 [skip ci] ([635571b](https://github.com/dafyddj/tmp-test-template-formula/commit/635571b2c5cbee6bb8ff36451f99bccdc65ab068))
* **release:** 2.1.10 [skip ci] ([11df22c](https://github.com/dafyddj/tmp-test-template-formula/commit/11df22c21724be7e51a97752f2092afd3ab1d5b4))
* **release:** 2.1.11 [skip ci] ([7d147d3](https://github.com/dafyddj/tmp-test-template-formula/commit/7d147d33953b46d3a1073ca1fddede390344fe95))
* **release:** 2.1.12 [skip ci] ([56da707](https://github.com/dafyddj/tmp-test-template-formula/commit/56da70720665d9e45ce2922307cb40b1b9dc14cf))
* **release:** 2.1.13 [skip ci] ([05c9db5](https://github.com/dafyddj/tmp-test-template-formula/commit/05c9db54641cd1e56c9c1fe61eca3be4e1bc999e))
* **release:** 2.1.14 [skip ci] ([9ec24f9](https://github.com/dafyddj/tmp-test-template-formula/commit/9ec24f9aecdfe4a1f41b45c513b2c655f48d7f5f))
* **release:** 2.1.15 [skip ci] ([653d314](https://github.com/dafyddj/tmp-test-template-formula/commit/653d31434b52c48ec5f0ba5d65fca95e63e1655d))
* **release:** 2.1.16 [skip ci] ([1ac7c4c](https://github.com/dafyddj/tmp-test-template-formula/commit/1ac7c4c8025dd76630763af801563a59719924a8))
* **release:** 2.1.17 [skip ci] ([9b88cf4](https://github.com/dafyddj/tmp-test-template-formula/commit/9b88cf416f13ae70f8afa51a9203d112a264c67e))
* **release:** 2.1.18 [skip ci] ([7da2867](https://github.com/dafyddj/tmp-test-template-formula/commit/7da28676b9e463d10f321aae0dd74b0edfe82671))
* **release:** 2.1.2 [skip ci] ([27e3be7](https://github.com/dafyddj/tmp-test-template-formula/commit/27e3be7b178547aaff3f9b74986dd282111a5797))
* **release:** 2.1.3 [skip ci] ([147760d](https://github.com/dafyddj/tmp-test-template-formula/commit/147760d19fdb652e947da4da287511605aff72d5))
* **release:** 2.1.4 [skip ci] ([f4c7226](https://github.com/dafyddj/tmp-test-template-formula/commit/f4c72269641de081c7d7bda334353c56b566c18e))
* **release:** 2.1.5 [skip ci] ([5eced87](https://github.com/dafyddj/tmp-test-template-formula/commit/5eced87a6aa2ed2f54d42ae5fc14bb37e0493925))
* **release:** 2.1.6 [skip ci] ([f0d1bf9](https://github.com/dafyddj/tmp-test-template-formula/commit/f0d1bf956ccbc761a55a1fd51fb4a9be76240027))
* **release:** 2.1.7 [skip ci] ([f2efbcf](https://github.com/dafyddj/tmp-test-template-formula/commit/f2efbcf447de2155aaad8b33c11ec17c270d603c))
* **release:** 2.1.8 [skip ci] ([cf3212d](https://github.com/dafyddj/tmp-test-template-formula/commit/cf3212d9a51a852fff828a6fa78148242e3293c0))
* **release:** 2.1.9 [skip ci] ([dc4f90b](https://github.com/dafyddj/tmp-test-template-formula/commit/dc4f90bb3ebf126000fc164fda8537e4ab65b218))
* **release:** 2.2.0 [skip ci] ([b55d593](https://github.com/dafyddj/tmp-test-template-formula/commit/b55d5931f1fe02e2b75f99602e450fdd260dbcb8))
* **release:** 2.2.1 [skip ci] ([9de820d](https://github.com/dafyddj/tmp-test-template-formula/commit/9de820d71f13b3e0ddcb18b0436a99696eda997e))
* **release:** 3.0.0 [skip ci] ([b7654c3](https://github.com/dafyddj/tmp-test-template-formula/commit/b7654c34a4322c47829c007aabf1a6bbb38b7627))
* **release:** 3.0.1 [skip ci] ([a2dd568](https://github.com/dafyddj/tmp-test-template-formula/commit/a2dd5684bbf44d14235a02acf7a62d08bef3c9dd))
* **release:** 3.0.2 [skip ci] ([8c7229d](https://github.com/dafyddj/tmp-test-template-formula/commit/8c7229dd2b515915659d79f42e53d38103a5a354))
* **release:** 3.0.3 [skip ci] ([13a4f29](https://github.com/dafyddj/tmp-test-template-formula/commit/13a4f29286ef5c5ac3b25fd013b8ebb3b0e9eae2))
* **release:** 3.0.4 [skip ci] ([5b99d99](https://github.com/dafyddj/tmp-test-template-formula/commit/5b99d9960786fa74b5f89e82fdf8a8ecb620eeb2))
* **release:** 3.0.5 [skip ci] ([4890b4a](https://github.com/dafyddj/tmp-test-template-formula/commit/4890b4af7faa46c900e6895d3d67a44100c25ce8))
* **release:** 3.0.6 [skip ci] ([5326328](https://github.com/dafyddj/tmp-test-template-formula/commit/53263283a7a154ff98925b6c2c0edda4e442ff3d))
* **release:** 3.0.7 [skip ci] ([cf7d7c0](https://github.com/dafyddj/tmp-test-template-formula/commit/cf7d7c0fa3e1eb4e309b85454d40a2363fe2569d))
* **release:** 3.0.8 [skip ci] ([f2c6454](https://github.com/dafyddj/tmp-test-template-formula/commit/f2c6454c2a8045e7e6dced3c4dab1eb9f65b23a6))
* **release:** 3.0.9 [skip ci] ([72ea25f](https://github.com/dafyddj/tmp-test-template-formula/commit/72ea25fdd355171b2aa1599357d3cf8839e2260b))
* **release:** 3.1.0 [skip ci] ([d05d444](https://github.com/dafyddj/tmp-test-template-formula/commit/d05d444148fb05faedcc0f7b0095dde8aa8da2f9))
* **release:** 3.1.1 [skip ci] ([10e23bc](https://github.com/dafyddj/tmp-test-template-formula/commit/10e23bc21960b97e08c77e5e0d59f3d6e97bf283))
* **release:** 3.2.0 [skip ci] ([a660762](https://github.com/dafyddj/tmp-test-template-formula/commit/a6607624171a6881a71870d6e81d0641d4b546f8))
* **release:** 3.2.1 [skip ci] ([e868561](https://github.com/dafyddj/tmp-test-template-formula/commit/e8685619ee94138c4d13226fd3c5102dc7336d10))
* **release:** 3.3.0 [skip ci] ([5067a67](https://github.com/dafyddj/tmp-test-template-formula/commit/5067a6718b95ca6cabd2bc0994a26d254abb10e3))
* **release:** 3.3.1 [skip ci] ([44b70cc](https://github.com/dafyddj/tmp-test-template-formula/commit/44b70ccd58c8545446a650843cccf8bb029de676))
* **release:** 3.3.2 [skip ci] ([af8ba86](https://github.com/dafyddj/tmp-test-template-formula/commit/af8ba86e82e240b6d15cef44d798cda314a33553))
* **release:** 3.3.3 [skip ci] ([a421e52](https://github.com/dafyddj/tmp-test-template-formula/commit/a421e5246a8b86af4f320968b6fcf035a3ff7b3c))
* **release:** 3.3.4 [skip ci] ([b4f16ba](https://github.com/dafyddj/tmp-test-template-formula/commit/b4f16ba41962c3306d4ef412bc8f0c4cfa017b83))
* **release:** 4.0.0 [skip ci] ([cef5b27](https://github.com/dafyddj/tmp-test-template-formula/commit/cef5b2740351c19e7b76389507bd496074cf1995))
* **release:** 4.0.1 [skip ci] ([995bf20](https://github.com/dafyddj/tmp-test-template-formula/commit/995bf205e4d941ceac138ba129fccdf9b0b84849))
* **release:** 4.0.2 [skip ci] ([3124e90](https://github.com/dafyddj/tmp-test-template-formula/commit/3124e9075e4e133b6ad3203136b813469e850d19))
* **release:** 4.0.3 [skip ci] ([b121de0](https://github.com/dafyddj/tmp-test-template-formula/commit/b121de0fe12cd8e69dc81120aa545fbd9cff8942))
* **release:** 4.0.4 [skip ci] ([596ae0d](https://github.com/dafyddj/tmp-test-template-formula/commit/596ae0d64cfa41e37bc6343e93e1a1ca7ee77808))
* **release:** 4.0.5 [skip ci] ([bb852f2](https://github.com/dafyddj/tmp-test-template-formula/commit/bb852f2a36141c9fca9bfe0b4d982392301d7fec))
* **release:** 4.0.6 [skip ci] ([93af398](https://github.com/dafyddj/tmp-test-template-formula/commit/93af398cda5c7f2289c3c7211722601d92d5e3e7))
* **release:** 4.0.7 [skip ci] ([dd19f43](https://github.com/dafyddj/tmp-test-template-formula/commit/dd19f43cfc367c69e05a1fb059ba7da0fa834869))
* **release:** 4.0.8 [skip ci] ([2846e42](https://github.com/dafyddj/tmp-test-template-formula/commit/2846e42e82b7c3d3f9f65533b5bcad406b997754))
* **release:** 4.0.9 [skip ci] ([96b581c](https://github.com/dafyddj/tmp-test-template-formula/commit/96b581c1d4ee1329ffac260a6c26e6854884cfcd))
* **release:** 4.1.0 [skip ci] ([e6e3016](https://github.com/dafyddj/tmp-test-template-formula/commit/e6e3016ed9173b8802a1a0c9b049fa8e7364e53f))
* **release:** 4.1.1 [skip ci] ([7d3d989](https://github.com/dafyddj/tmp-test-template-formula/commit/7d3d9892233be9cc85c9929f4f30f9a97e0b2b89))
* **release:** 4.2.0 [skip ci] ([02ce903](https://github.com/dafyddj/tmp-test-template-formula/commit/02ce903e2ba9c6553dfaf58c7ae022ce964b8b59))
* **release:** 4.2.1 [skip ci] ([e668832](https://github.com/dafyddj/tmp-test-template-formula/commit/e668832b76604b3890b7f514fa36105314145382))
* **release:** 4.2.2 [skip ci] ([c0c3f23](https://github.com/dafyddj/tmp-test-template-formula/commit/c0c3f235e0ec8ec56d7679b78ef2ea55a0f9a17a))
* **release:** 4.3.0 [skip ci] ([ec90f64](https://github.com/dafyddj/tmp-test-template-formula/commit/ec90f64469487492cc87e5aafa5e156bb6a975b6))
* **release:** 4.3.1 [skip ci] ([2f057b0](https://github.com/dafyddj/tmp-test-template-formula/commit/2f057b0cfd3fdf55129467f1c6bab41b3ae60844))
* **release:** 4.3.2 [skip ci] ([889546b](https://github.com/dafyddj/tmp-test-template-formula/commit/889546bad225e9b38d7f817cb4a1b2e5c0ad1951))
* **release:** 4.3.3 [skip ci] ([5d36fda](https://github.com/dafyddj/tmp-test-template-formula/commit/5d36fda7a473a5aefbf4ff80cb9747cf608771c9))
* **release:** 4.3.4 [skip ci] ([b3b8e5e](https://github.com/dafyddj/tmp-test-template-formula/commit/b3b8e5e974e78b299495065b548755787285538b))
* **release:** 4.3.5 [skip ci] ([d0d9cce](https://github.com/dafyddj/tmp-test-template-formula/commit/d0d9cce017266ab7198b10ce68d56c7a038a2162))
* **release:** 4.3.6 [skip ci] ([ab99109](https://github.com/dafyddj/tmp-test-template-formula/commit/ab9910936388b657e08814c2c782a4be7efc76bd))
* **release:** 4.3.7 [skip ci] ([63158c0](https://github.com/dafyddj/tmp-test-template-formula/commit/63158c0aa97b38e43715e0ff0e865b5515b977f4))
* **release:** 4.3.8 [skip ci] ([0ae2aa7](https://github.com/dafyddj/tmp-test-template-formula/commit/0ae2aa7a4003d29a8f09d75e2c518008567251aa))
* **release:** 5.0.0 [skip ci] ([2f76e06](https://github.com/dafyddj/tmp-test-template-formula/commit/2f76e066609ced49fd457795f49a81aea18388fd))
* **release:** 5.0.1 [skip ci] ([3ff398b](https://github.com/dafyddj/tmp-test-template-formula/commit/3ff398bce4ec18bcc5991ffec4e33a57b6fdf064))
* **release:** 5.0.10 [skip ci] ([65735fe](https://github.com/dafyddj/tmp-test-template-formula/commit/65735fed56710f9840effee936fdddbf539fff34))
* **release:** 5.0.11 [skip ci] ([d4c5ee3](https://github.com/dafyddj/tmp-test-template-formula/commit/d4c5ee3c6945e03d8cf17f1e723a2dbf3a2f0fde))
* **release:** 5.0.12 [skip ci] ([fd8430b](https://github.com/dafyddj/tmp-test-template-formula/commit/fd8430b203101eee8d124f5734ba678e71ac3e11))
* **release:** 5.0.13 [skip ci] ([1173911](https://github.com/dafyddj/tmp-test-template-formula/commit/11739114bfc691396f7a7b79691b3a90ec9c7737))
* **release:** 5.0.14 [skip ci] ([19d3eaf](https://github.com/dafyddj/tmp-test-template-formula/commit/19d3eafc6973b4b482585aad3820a79a6f1bd1db))
* **release:** 5.0.15 [skip ci] ([c9609c7](https://github.com/dafyddj/tmp-test-template-formula/commit/c9609c73001b090806e12f91bcd0dfbed8442995))
* **release:** 5.0.16 [skip ci] ([06280b5](https://github.com/dafyddj/tmp-test-template-formula/commit/06280b5ce47ce3f6643e462b2c6863a427ce1be3))
* **release:** 5.0.17 [skip ci] ([b0e28b9](https://github.com/dafyddj/tmp-test-template-formula/commit/b0e28b9a5924185427a039eaf68a0a488ea59be7))
* **release:** 5.0.18 [skip ci] ([591880d](https://github.com/dafyddj/tmp-test-template-formula/commit/591880d75590c0a326bbb8b4f0ff688cf156d31a))
* **release:** 5.0.19 [skip ci] ([db896ca](https://github.com/dafyddj/tmp-test-template-formula/commit/db896ca3851aa976820ed1ae62e12c547d63633c))
* **release:** 5.0.2 [skip ci] ([ac9c2e8](https://github.com/dafyddj/tmp-test-template-formula/commit/ac9c2e872e4e35b9b8af373c4a8415b123ed887f))
* **release:** 5.0.20 [skip ci] ([4f32e04](https://github.com/dafyddj/tmp-test-template-formula/commit/4f32e049aacadfabadc8017a6ff036abb85890cb))
* **release:** 5.0.21 [skip ci] ([9977b8a](https://github.com/dafyddj/tmp-test-template-formula/commit/9977b8ad2a6fc52de25e8b10e9ef70e8af4f7393))
* **release:** 5.0.22 [skip ci] ([7c3eb89](https://github.com/dafyddj/tmp-test-template-formula/commit/7c3eb897d183bfa2219ea60ebd53b7f34b027b15))
* **release:** 5.0.3 [skip ci] ([f84c6cf](https://github.com/dafyddj/tmp-test-template-formula/commit/f84c6cfaadafc1088a83018ddad452fce3dc20d5))
* **release:** 5.0.4 [skip ci] ([643b8f1](https://github.com/dafyddj/tmp-test-template-formula/commit/643b8f1d76520b3b0004729467af068399768f10))
* **release:** 5.0.5 [skip ci] ([169ccce](https://github.com/dafyddj/tmp-test-template-formula/commit/169ccce59ecc5b82c5bfcb61c4ccc68e8991c4f8))
* **release:** 5.0.6 [skip ci] ([d97a51d](https://github.com/dafyddj/tmp-test-template-formula/commit/d97a51d379324d2fd8e24a54ec3ad685498a0ce3))
* **release:** 5.0.7 [skip ci] ([6c3fb20](https://github.com/dafyddj/tmp-test-template-formula/commit/6c3fb20796a5662d3e53567502593264432474d3))
* **release:** 5.0.8 [skip ci] ([e486d1d](https://github.com/dafyddj/tmp-test-template-formula/commit/e486d1d6ae2b654a9b78fd8caad9a32c9680fee0))
* **release:** 5.0.9 [skip ci] ([0d1f0dd](https://github.com/dafyddj/tmp-test-template-formula/commit/0d1f0ddb862096bb11c2c3467d901e30749ad454))
* **release:** 5.1.0 [skip ci] ([f650941](https://github.com/dafyddj/tmp-test-template-formula/commit/f65094106429f456e7a77f15eea63b3df8d172e9))
* rename `rstcheck` hook repo ([848dcec](https://github.com/dafyddj/tmp-test-template-formula/commit/848dcec52a09e8a5ce7ce1aaa963706889728cad))
* **rubocop:** allow use of `YAML.load` for `_mapdata.rb` [skip ci] ([5830a8c](https://github.com/dafyddj/tmp-test-template-formula/commit/5830a8ce976f124d10abf081cb26fde644b8e512))
* **rubocop:** move `LineLength` cop from `Metrics` to `Layout` ([5db1d7c](https://github.com/dafyddj/tmp-test-template-formula/commit/5db1d7c468882cc13ad89a001e46a667b7221efb))
* **rubocop:** use org-wide standard settings for `Metrics/BlockLength` [skip ci] ([19cded8](https://github.com/dafyddj/tmp-test-template-formula/commit/19cded8567da32aa15a664efbba6705808121c0a))
* **semantic-release:** move pre-commit script back to root dir ([4601d38](https://github.com/dafyddj/tmp-test-template-formula/commit/4601d38289f5a3d880e819bd2919c93f315973a6))
* **semantic-release:** move pre-commit script to `bin/` subdir ([f341bdb](https://github.com/dafyddj/tmp-test-template-formula/commit/f341bdb8ef057aa8189619e7751b8e6def9d84b3))
* **semantic-release:** replace broken `m2r` with `m2r2` [skip ci] ([8d739b9](https://github.com/dafyddj/tmp-test-template-formula/commit/8d739b906d06f1977bfcd551f28224395e90f7ec))
* **shellcheck:** switch hook for `shellcheck` ([f1ad843](https://github.com/dafyddj/tmp-test-template-formula/commit/f1ad843d2907bef5d85586a590cd626c8c448804)), closes [#226](https://github.com/dafyddj/tmp-test-template-formula/issues/226)
* standardise structure (`.gitignore` & `_mapdata.rb`) [skip ci] ([6d17eb0](https://github.com/dafyddj/tmp-test-template-formula/commit/6d17eb01308cfcad1e3d129f81dfa481b9ccea56))
* update `CODEOWNERS` & `.yamllint` re: `kitchen-vagrant` [skip ci] ([d9ee807](https://github.com/dafyddj/tmp-test-template-formula/commit/d9ee80784bd73ceb425b8c12103381a929d86178))
* use `semantic-release` cross-formula standard structure ([d51c4e3](https://github.com/dafyddj/tmp-test-template-formula/commit/d51c4e38c8cf946922bcc1472e01215b935e1f44))
* use `semantic-release` cross-formula standard structure ([582296a](https://github.com/dafyddj/tmp-test-template-formula/commit/582296a6a951ab04b5fb61d61020e62754c1aad0))
* use `semantic-release` cross-formula standard structure ([4a2e848](https://github.com/dafyddj/tmp-test-template-formula/commit/4a2e848e077a39d98b927b2583933cf1a8d72363))
* use `semantic-release` cross-formula standard structure ([4a71611](https://github.com/dafyddj/tmp-test-template-formula/commit/4a71611c0d9c11e9e597f50e1ad24bab02ad71b6))
* **workflows:** fix linting ([5aee218](https://github.com/dafyddj/tmp-test-template-formula/commit/5aee218b987dc1e6cf82f00d2f18f91973dacfcb))
* **yamllint:** add `.git/` to ignores [skip ci] ([d356e20](https://github.com/dafyddj/tmp-test-template-formula/commit/d356e20411d67eb760dbabc9f40f2aca555655db))
* **yamllint:** update ignored paths and add `octal-values` [skip ci] ([44ce327](https://github.com/dafyddj/tmp-test-template-formula/commit/44ce32792515a37fd58310e7620235c4d480a323))

# [5.1.0](https://github.com/saltstack-formulas/template-formula/compare/v5.0.22...v5.1.0) (2025-07-31)


### Features

* **workflows:** dry-run `semantic-release` in GitHub Actions ([764cd4c](https://github.com/saltstack-formulas/template-formula/commit/764cd4ca8a735b4995162c4be8fea57e3dabba81))

## [5.0.22](https://github.com/saltstack-formulas/template-formula/compare/v5.0.21...v5.0.22) (2025-06-24)


### Continuous Integration

* **workflows:** improve `pre-commit` caching ([38d87fc](https://github.com/saltstack-formulas/template-formula/commit/38d87fc4d19da0c1c431d25b8bf4680e13f287be))
* **workflows:** remove trailing comma ([5039aba](https://github.com/saltstack-formulas/template-formula/commit/5039aba8fb809d427c31091b7b7e189190234b83))


### Tests

* **pre-commit:** check JavaScript files using standardJS ([b0c7df4](https://github.com/saltstack-formulas/template-formula/commit/b0c7df414a53b6a5da970170bb66dd7ffa75ae30))

## [5.0.21](https://github.com/saltstack-formulas/template-formula/compare/v5.0.20...v5.0.21) (2025-06-16)


### Continuous Integration

* **workflows:** add testing for some platforms to GitHub Actions ([7eb8b73](https://github.com/saltstack-formulas/template-formula/commit/7eb8b737ce52ecf4e1ad0977732b53d81a28dbe7))
* update images for v3006.12 & v3007.4 ([52f7dae](https://github.com/saltstack-formulas/template-formula/commit/52f7dae788ba58ab1be76f04e2749548a392c2f0))
* **kitchen+gitlab:** remove OpenSUSE 15.5 (EOL) ([54bdd66](https://github.com/saltstack-formulas/template-formula/commit/54bdd661f8453ee2d4fce5d0be83e1b67b4a92f6))
* **renovate:** disable Bundler (Ruby Gems) updates ([8a18188](https://github.com/saltstack-formulas/template-formula/commit/8a1818868966d51a4faae4aab30d0de4b4f0eb3f))
* **renovate:** enable and group GitHub Actions updates ([0bb9c03](https://github.com/saltstack-formulas/template-formula/commit/0bb9c033f635355cf6207ab5b83039742fbae2d2))
* **renovate:** use `groupManager` preset ([4061b00](https://github.com/saltstack-formulas/template-formula/commit/4061b00c81a5d64e7cd77f588035bc592023e060))
* **renovate:** use org's default preset ([ef5b642](https://github.com/saltstack-formulas/template-formula/commit/ef5b642c0129a24b80ba4a28661180ee2fe16821))
* **workflows:** checkout treeless clone w/ history/tags for `commitlint` ([e128c82](https://github.com/saltstack-formulas/template-formula/commit/e128c8203fa949c198e2cb362f38f891e224d9db))
* **workflows:** exception for `line-length` ([f6eb9cf](https://github.com/saltstack-formulas/template-formula/commit/f6eb9cf0cf8a582e08e98a2ade35c26ca4269bb6))
* allow failures on all `master` test instances ([aeb7926](https://github.com/saltstack-formulas/template-formula/commit/aeb7926b927f2c7c9f02442f133f680b45f58dba))


### Tests

* **yamllint:** allow for long words and Renovate-specific comments ([43a31a3](https://github.com/saltstack-formulas/template-formula/commit/43a31a39d6bd8e8a4121e07d6fb718f8a24f5b1e))

## [5.0.20](https://github.com/saltstack-formulas/template-formula/compare/v5.0.19...v5.0.20) (2025-06-09)


### Tests

* **pre-commit:** check for Git merge conflict markers ([895d4f9](https://github.com/saltstack-formulas/template-formula/commit/895d4f90ebd851c74b1dd0b121f3a7f9d8618771))

## [5.0.19](https://github.com/saltstack-formulas/template-formula/compare/v5.0.18...v5.0.19) (2025-06-06)


### Continuous Integration

* **gitlab-ci:** improve caching for `bundler` and `test_conversion` job ([6833620](https://github.com/saltstack-formulas/template-formula/commit/683362093eddd47f0d2b16d49a059afe78e42781))
* **gitlab-ci:** optimise test instance caching ([efbd8c6](https://github.com/saltstack-formulas/template-formula/commit/efbd8c682086aade92671e083496004888c226ff))
* update images for v3006.11 ([a9c769a](https://github.com/saltstack-formulas/template-formula/commit/a9c769ae170f8262e35def4d2bda5afc087eca18))
* update images for v3007.3 ([747c337](https://github.com/saltstack-formulas/template-formula/commit/747c3370afec0e0600c3f7b7981705356c6f15ae))
* **gitlab-ci:** improve `pre-commit` caching ([fae68d8](https://github.com/saltstack-formulas/template-formula/commit/fae68d8339731bfaf88be2762d3ee8dde4a6b758))


### Tests

* **kitchen:** drop timeout to `60` seconds ([2817f52](https://github.com/saltstack-formulas/template-formula/commit/2817f525cb7b1efa2e1f5c6c181437350b4a6bf0))

## [5.0.18](https://github.com/saltstack-formulas/template-formula/compare/v5.0.17...v5.0.18) (2025-06-04)


### Continuous Integration

* **gitlab-ci:** run `commitlint` in `pre-commit` job ([a5a6962](https://github.com/saltstack-formulas/template-formula/commit/a5a6962840a35462482425d6c93abde63504d8a2))
* **workflows:** add new `main` workflow running `pre-commit` ([5bc2f5d](https://github.com/saltstack-formulas/template-formula/commit/5bc2f5da1d4cda245aff13180906bdd88e37e700))


### Tests

* **github-actions:** check GitHub Actions using `check-jsonschema` ([1600e5f](https://github.com/saltstack-formulas/template-formula/commit/1600e5f92695bcd377aba31f7f877f6c6dff89da))

## [5.0.17](https://github.com/saltstack-formulas/template-formula/compare/v5.0.16...v5.0.17) (2025-06-04)


### Tests

* update `commitlint` hook to v19.8.1 ([0d060d9](https://github.com/saltstack-formulas/template-formula/commit/0d060d93e3c54f9ed2ebb620d6b0ff62691c05e0))

## [5.0.16](https://github.com/saltstack-formulas/template-formula/compare/v5.0.15...v5.0.16) (2025-05-24)


### Continuous Integration

* **gitlab-ci:** remove `py3` from instance names ([076a6cb](https://github.com/saltstack-formulas/template-formula/commit/076a6cb875a880869685fe6fea31ac3a7f939203))
* **gitlab-ci:** specify version for `dind` service image ([235a963](https://github.com/saltstack-formulas/template-formula/commit/235a963b6b771ae99543f3ddb0b2031d73936d46))
* **renovate:** enable and group Pre-commit hook non-major updates ([d21a192](https://github.com/saltstack-formulas/template-formula/commit/d21a192c1c1ad062f631a7da9a1e160ed4866460))
* **renovate:** group GitLab CI Docker images together ([0a8dd28](https://github.com/saltstack-formulas/template-formula/commit/0a8dd28c355f77f019fc595e5fc9c5883c84d46d))
* **renovate:** improve wording ([079ec01](https://github.com/saltstack-formulas/template-formula/commit/079ec0189873b15f3e9f691b9ac0fa6f3b2d007a))
* **renovate:** include digest updates in GitLab images group ([6146090](https://github.com/saltstack-formulas/template-formula/commit/614609094b522f4ec711f5690532934bec8878ce))
* **renovate:** limit schedule to Tuesdays before 6AM ([9b3d017](https://github.com/saltstack-formulas/template-formula/commit/9b3d017bbd678febd2285bf6a39c12d2b59f734e))
* update images for v3007.2 ([0741129](https://github.com/saltstack-formulas/template-formula/commit/0741129b2d11ce8d02a4f13cfab857b7c2cd3e5d))
* **gitlab-ci:** simplify list of TestKitchen instances ([888286a](https://github.com/saltstack-formulas/template-formula/commit/888286a82a7ec53c9ce5022d70368a447466881c))
* **renovate:** enable Bundler (Ruby Gems) updates ([2781f77](https://github.com/saltstack-formulas/template-formula/commit/2781f77703d88b09973a83818abb81087a68e670))


### Styles

* **gitlab-ci:** order instances alphabetically for consistency ([06cfa97](https://github.com/saltstack-formulas/template-formula/commit/06cfa9739a2cf12ef0120c3ca0564f613e2fe001))

## [5.0.15](https://github.com/saltstack-formulas/template-formula/compare/v5.0.14...v5.0.15) (2025-05-09)


### Tests

* **yamllint:** exclude auto-generated Copier files from linting ([6cda6ad](https://github.com/saltstack-formulas/template-formula/commit/6cda6adc52c836406eaeee618ae2228db3e0a0bc))

## [5.0.14](https://github.com/saltstack-formulas/template-formula/compare/v5.0.13...v5.0.14) (2025-05-07)


### Tests

* **kitchen:** avoid lengthy waits for containers ([2db5865](https://github.com/saltstack-formulas/template-formula/commit/2db58656b4dbccea0b50d3debdf2da9859f86ed6))

## [5.0.13](https://github.com/saltstack-formulas/template-formula/compare/v5.0.12...v5.0.13) (2025-05-07)


### Continuous Integration

* ignore `yamllint rule:line-length` for Docker images ([ec26bf1](https://github.com/saltstack-formulas/template-formula/commit/ec26bf1adba0833df44170978ae65492a2976b80))
* **renovate:** initial commit of basic Renovate config ([bd7464b](https://github.com/saltstack-formulas/template-formula/commit/bd7464b80705a2b26a1f902ba9f1ff270680239f))
* add mapdata for new os ([a1bdd12](https://github.com/saltstack-formulas/template-formula/commit/a1bdd126089d1e6d222580fe931e2632a9df1ed5))
* remove EOL images & allow failure of `amazonlinux-2` ([6e6d524](https://github.com/saltstack-formulas/template-formula/commit/6e6d524ea4f2bf55115be2517c3556a7477138b5))
* update `ci-commitlint` to v1.1.76 ([6cf5ef9](https://github.com/saltstack-formulas/template-formula/commit/6cf5ef9957f87a03bb4a4de4315e81fb712d923e))
* update `ci-docker-python-ruby` to v2.2.45 ([78f551d](https://github.com/saltstack-formulas/template-formula/commit/78f551d6392160eeff181fc9e8c4aa53b2fca66d))
* update `ci-pre-commit` to v2.4.10 ([f266a50](https://github.com/saltstack-formulas/template-formula/commit/f266a5065b93296b7e5c125a5991f381ed1a36f5))
* update `ci-pre-commit` to v2.4.10 ([28d90f5](https://github.com/saltstack-formulas/template-formula/commit/28d90f506f5aae1d849f7324519ab5c74464126b))
* update `ci-pre-commit` to v2.4.10 ([20de9ca](https://github.com/saltstack-formulas/template-formula/commit/20de9ca6386e5b8ce76dffd40978d935f9c0dc3b))
* use latest test images ([417ca53](https://github.com/saltstack-formulas/template-formula/commit/417ca530dd961d47af6ed2132fddbca835989e6d))
* use latest test images ([5fb252c](https://github.com/saltstack-formulas/template-formula/commit/5fb252c0340146cbacdb339cb1a5556f0f85aa8a))
* use latest test images ([b41b8dc](https://github.com/saltstack-formulas/template-formula/commit/b41b8dc94bfdb658a881a6f7bded22e912bbb323))
* use latest test images ([579a43b](https://github.com/saltstack-formulas/template-formula/commit/579a43b7a9c80ccb3bad179c61ee2af50ac139bb))
* use latest test images ([b71ff75](https://github.com/saltstack-formulas/template-formula/commit/b71ff7523ae70b8501479ca943b885a1c283bf38))
* use latest test images ([d53ceae](https://github.com/saltstack-formulas/template-formula/commit/d53ceae71bfb149e766f0bde28a20a469f2ab5f3))


### Tests

* **gitlab-ci:** check GitLab CI config using `check-jsonschema` ([670c139](https://github.com/saltstack-formulas/template-formula/commit/670c139f6b84667c9e9259ddf661f366753f18d4))
* **pre-commit:** update deprecated stage name ([a82b2ed](https://github.com/saltstack-formulas/template-formula/commit/a82b2eda6d7968689975cf0bdadbff19c4841ed5))

## [5.0.12](https://github.com/saltstack-formulas/template-formula/compare/v5.0.11...v5.0.12) (2024-01-02)


### Bug Fixes

* **suse:** correct OS grain ([6aee580](https://github.com/saltstack-formulas/template-formula/commit/6aee5804d3d4282322c6421befefa7b803eca699))

## [5.0.11](https://github.com/saltstack-formulas/template-formula/compare/v5.0.10...v5.0.11) (2023-12-04)


### Continuous Integration

* update container images ([963522f](https://github.com/saltstack-formulas/template-formula/commit/963522f342f34c30b3f222642eca71da73bdcc32))


### Tests

* **rubocop:** switch to using `pre-commit`'s built-in file filtering ([c3b4c14](https://github.com/saltstack-formulas/template-formula/commit/c3b4c1407051cda4421914921947f17de3101c6b))
* **rubocop:** use `AllowedMethods` not deprecated `IgnoredMethods` ([9261a27](https://github.com/saltstack-formulas/template-formula/commit/9261a27794137490a8810522d6541a62a75a2011))

## [5.0.10](https://github.com/saltstack-formulas/template-formula/compare/v5.0.9...v5.0.10) (2023-11-13)


### Bug Fixes

* broken install-hooks due to saltlint v0.8.0 ([7da11c9](https://github.com/saltstack-formulas/template-formula/commit/7da11c9c3ace8efc379cdec804420ca810e43548))


### Continuous Integration

* update the container images and refactor steps ([b84343e](https://github.com/saltstack-formulas/template-formula/commit/b84343ef831832c7b02326506d2398ef1d6fb67c))
* **commitlint:** update action versions ([c69928d](https://github.com/saltstack-formulas/template-formula/commit/c69928d2495966daaf4ca8bf82dd53e999e1739c))
* update `pre-commit` configuration inc. for pre-commit.ci [skip ci] ([32518b9](https://github.com/saltstack-formulas/template-formula/commit/32518b9798ae537f9448214126fb1bc11f2a0ac7))
* **gitlab-ci:** fix test conversion job (reset back to [#249](https://github.com/saltstack-formulas/template-formula/issues/249)) [skip ci] ([6ea1cc2](https://github.com/saltstack-formulas/template-formula/commit/6ea1cc2f4066796ca00c2bf0cb630ef4302df660))


### Styles

* **default.sls:** fix minor typo ([3d1581e](https://github.com/saltstack-formulas/template-formula/commit/3d1581e72611bfdac1ae14c57b69921c45f6b886))
* **inspec:** fix whitespace ([1df9861](https://github.com/saltstack-formulas/template-formula/commit/1df98610848bff149cb7c55549d691ca960005f9))


### Tests

* **_mapdata:** add verification file for `ubuntu-22` [skip ci] ([9349c83](https://github.com/saltstack-formulas/template-formula/commit/9349c838742a1396c092311e2529e80d3d76fabd))
* **pre-commit:** switch to using `pre-commit`'s built-in file filtering ([46130c4](https://github.com/saltstack-formulas/template-formula/commit/46130c4c092c89dd372f2a3f3b14e7568375d067))
* **pre-commit:** update `pre-commit` hooks ([2bd3ef9](https://github.com/saltstack-formulas/template-formula/commit/2bd3ef9a1835db081a86d3ea0f4434e3e17ce1a7))
* **rstcheck:** ignore Markdown-style links as false positives ([b2c28aa](https://github.com/saltstack-formulas/template-formula/commit/b2c28aa906fcce406b01523e7b7eccd04e658984))
* **system.rb:** add support for `mac_os_x` [skip ci] ([d46507b](https://github.com/saltstack-formulas/template-formula/commit/d46507ba82b2a197e1275d7c258f7245862c2662))

## [5.0.9](https://github.com/saltstack-formulas/template-formula/compare/v5.0.8...v5.0.9) (2022-04-25)


### Continuous Integration

* **gitlab-ci:** use Node `16.x` for `pre-commit` in test conversion job ([a1a46ae](https://github.com/saltstack-formulas/template-formula/commit/a1a46ae38995f1506c3574c7818cfc8fcc887d6c))
* **kitchen+gitlab:** update for new pre-salted images [skip ci] ([801be3d](https://github.com/saltstack-formulas/template-formula/commit/801be3d974abdc28e786d4ac462f018db45a891b))


### Tests

* **_mapdata:** add verification file for `fedora-35` [skip ci] ([6f02d2c](https://github.com/saltstack-formulas/template-formula/commit/6f02d2c28a7d3fe1449b93d862d02268344aa475))
* **_mapdata:** add verification file for `fedora-36` [skip ci] ([4a38a29](https://github.com/saltstack-formulas/template-formula/commit/4a38a292d66563984505ed082166b25f831fb460))

## [5.0.8](https://github.com/saltstack-formulas/template-formula/compare/v5.0.7...v5.0.8) (2022-02-23)


### Styles

* fix typo ([68d5ba0](https://github.com/saltstack-formulas/template-formula/commit/68d5ba0507ad0d10d51934f68fcea78470003669))

## [5.0.7](https://github.com/saltstack-formulas/template-formula/compare/v5.0.6...v5.0.7) (2022-02-17)


### Bug Fixes

* **libmapstack:** allow mapping by booleans and numbers ([bb3a7ea](https://github.com/saltstack-formulas/template-formula/commit/bb3a7ea0b208eeb2b6472ca9cb011935032c0356))


### Code Refactoring

* **libmatchers:** match default type with docs ([8f847be](https://github.com/saltstack-formulas/template-formula/commit/8f847bebfd4809b9c4acbfc1c20c1738243f9fd7))


### Styles

* **libsaltcli:** fix comments to jinja comments ([e1735f4](https://github.com/saltstack-formulas/template-formula/commit/e1735f47f8e7af13d8d3d4be9206851560e30c52))

## [5.0.6](https://github.com/saltstack-formulas/template-formula/compare/v5.0.5...v5.0.6) (2022-02-15)


### Documentation

* **map.jinja:** fix path to post-map.jinja in docs ([d64cd75](https://github.com/saltstack-formulas/template-formula/commit/d64cd75f62b7ad20f61de85e19534da492f55eda))


### Tests

* **system:** add `build_platform_codename` [skip ci] ([65cf22c](https://github.com/saltstack-formulas/template-formula/commit/65cf22c436903a65f93b9f5e708d8639499d542b))

## [5.0.5](https://github.com/saltstack-formulas/template-formula/compare/v5.0.4...v5.0.5) (2022-02-13)


### Bug Fixes

* **libsaltcli+libmatchers:** ensure Salt client API detection [skip ci] ([6eb2073](https://github.com/saltstack-formulas/template-formula/commit/6eb2073d02ff8006dac86c59e683ae983ecccd25))


### Code Refactoring

* **shellcheck:** fix violation ([4ee6387](https://github.com/saltstack-formulas/template-formula/commit/4ee6387bf97aeb9c965bd2638ba934208d00874c))


### Continuous Integration

* **gitlab-ci:** update `dind-ruby-bionic` (use Python 3.7 for pre-commit) ([8ff2152](https://github.com/saltstack-formulas/template-formula/commit/8ff2152b32262fe2082f68e42532f3c0178f55b0))
* update linters to latest versions [skip ci] ([a284a56](https://github.com/saltstack-formulas/template-formula/commit/a284a566b4284966c7bbbc9da7ad182083a60796))
* **kitchen+ci:** update with `3004` pre-salted images/boxes [skip ci] ([ea37971](https://github.com/saltstack-formulas/template-formula/commit/ea379716bea3d9d93a88671b8c0ae368033dcd62))
* **kitchen+gitlab:** update for new pre-salted images [skip ci] ([fd34718](https://github.com/saltstack-formulas/template-formula/commit/fd347183f992f2d0511986744f65c715445d7c5e))
* **proxy:** allow rubygems proxy in gemfile ([7109cfd](https://github.com/saltstack-formulas/template-formula/commit/7109cfd411804514607a70edc3339e011e1db1cc))

## [5.0.4](https://github.com/saltstack-formulas/template-formula/compare/v5.0.3...v5.0.4) (2021-11-16)


### Code Refactoring

* **map.jinja:** standardise v5 structure [skip ci] ([bf9a9bd](https://github.com/saltstack-formulas/template-formula/commit/bf9a9bd20482b5a5a748933094f58a0f88b41aee))


### Continuous Integration

* **kitchen:** use `pillars_from_directories` under `provisioner` ([5f80cf2](https://github.com/saltstack-formulas/template-formula/commit/5f80cf2b7dc9dc90cd2de2121787c3b7b5efc6bf))
* **kitchen+ci:** update with latest CVE pre-salted images [skip ci] ([6c5809d](https://github.com/saltstack-formulas/template-formula/commit/6c5809d067ae5ae7db52c17bda30b0cd133b7966))


### Tests

* **pillar:** use static test/salt/pillar/top.sls ([7708e12](https://github.com/saltstack-formulas/template-formula/commit/7708e1292303431d9ac4a46f0c4123cc95b98bc6))

## [5.0.3](https://github.com/saltstack-formulas/template-formula/compare/v5.0.2...v5.0.3) (2021-08-19)


### Bug Fixes

* **convert-formula.sh:** add `~` to reST underlining during conversion ([80ed8cd](https://github.com/saltstack-formulas/template-formula/commit/80ed8cd4153f99ec0acaac2996387f565981e7aa))
* **convert-formula.sh:** fix reST underlining during conversion ([11068af](https://github.com/saltstack-formulas/template-formula/commit/11068afae9a3b6957695b79f92b4588388a13632))


### Continuous Integration

* **3003.1:** update inc. AlmaLinux, Rocky & `rst-lint` [skip ci] ([be3ee0b](https://github.com/saltstack-formulas/template-formula/commit/be3ee0be5148ab598a613342e902284ffb547628))
* **gemfile+lock:** use `ssf` customised `inspec` repo [skip ci] ([3c7fb0f](https://github.com/saltstack-formulas/template-formula/commit/3c7fb0fca0498d7fd5b2e23c763a14e9258c051f))
* **gitlab:** update `dind-ruby-bionic` with ruby 2.7.1 ([b2fe67a](https://github.com/saltstack-formulas/template-formula/commit/b2fe67a79d582313b6fd2468441141eae2705ae2))
* **kitchen:** move `provisioner` block & update `run_command` [skip ci] ([29df15e](https://github.com/saltstack-formulas/template-formula/commit/29df15e21ca972915b4ac5718c65c9aa6305eaff))
* **kitchen+ci:** update with latest `3003.2` pre-salted images [skip ci] ([1b8604d](https://github.com/saltstack-formulas/template-formula/commit/1b8604dd02907ea6da50c0ab539dd510f9fb755b))
* add `arch-master` to matrix and update `.travis.yml` [skip ci] ([7e74001](https://github.com/saltstack-formulas/template-formula/commit/7e74001c05292eb313a8f4a539784cdf94e232a0))
* add Debian 11 Bullseye & update `yamllint` configuration [skip ci] ([e14f830](https://github.com/saltstack-formulas/template-formula/commit/e14f83019a97ea49b4b056c6a9c2f51cac7887a9))
* **kitchen+gitlab:** adjust matrix to add `3003` [skip ci] ([c99c5a1](https://github.com/saltstack-formulas/template-formula/commit/c99c5a1b68cfe2374f38e1577515efd73c58a610))
* **kitchen+gitlab:** remove Ubuntu 16.04 & Fedora 32 (EOL) [skip ci] ([858ef8a](https://github.com/saltstack-formulas/template-formula/commit/858ef8a2b7097421a5073b0963c8b29ec3840bf3))


### Documentation

* **map.jinja:** fix `rst-lint` violation [skip ci] ([e43d6ce](https://github.com/saltstack-formulas/template-formula/commit/e43d6ce83f4cacfd70a5df3bbc53e22a9b442b24))
* **map.jinja:** make section headings consistent with other docs ([40277fc](https://github.com/saltstack-formulas/template-formula/commit/40277fc582a62d2255b478fb0b880eda1f46d77a))


### Tests

* **_mapdata:** add verification file for `debian-11` [skip ci] ([98edfd3](https://github.com/saltstack-formulas/template-formula/commit/98edfd3ac403353e9bd7d1d335e9ab48af3f1892))
* **_mapdata:** add verification file for `fedora-34` [skip ci] ([79587c4](https://github.com/saltstack-formulas/template-formula/commit/79587c422c0d30dc8ce203021afc63b62d4cbdf3))
* **alma+rocky:** add platforms (based on CentOS 8) [skip ci] ([ec7ede0](https://github.com/saltstack-formulas/template-formula/commit/ec7ede04077566dd3bc69ac3032b09ffcc3b7876))

## [5.0.2](https://github.com/saltstack-formulas/template-formula/compare/v5.0.1...v5.0.2) (2021-04-14)


### Bug Fixes

* **convert-formula.sh:** replace instances of `template-formula` for CI ([537fe65](https://github.com/saltstack-formulas/template-formula/commit/537fe65d456741e64823af33865f34457e0e3853)), closes [#231](https://github.com/saltstack-formulas/template-formula/issues/231)


### Tests

* standardise use of `share` suite & `_mapdata` state [skip ci] ([bbe1c78](https://github.com/saltstack-formulas/template-formula/commit/bbe1c7840990790eb2df564e96cc9b465093eb62))

## [5.0.1](https://github.com/saltstack-formulas/template-formula/compare/v5.0.0...v5.0.1) (2021-03-09)


### Bug Fixes

* **convert-formula:** `_mapdata` control name must use the formula one ([1f3600d](https://github.com/saltstack-formulas/template-formula/commit/1f3600d66fd710bd1a41cb937cb345369d0e3e18))

# [5.0.0](https://github.com/saltstack-formulas/template-formula/compare/v4.3.8...v5.0.0) (2021-03-09)


### Bug Fixes

* **inspec:** validate `map.jinja` configuration ([41d222e](https://github.com/saltstack-formulas/template-formula/commit/41d222e30c0da10fabeea23a7ab2886f02ea6479))


### Continuous Integration

* **kitchen+ci:** use latest pre-salted images (after CVE) [skip ci] ([6453145](https://github.com/saltstack-formulas/template-formula/commit/6453145da16ab73c7307d14a5b864a91a5573c68))


### Features

* **map:** update to v5 `map.jinja` ([42e1932](https://github.com/saltstack-formulas/template-formula/commit/42e19322c9c4d91a6cfa1e406723b5a799f33f80))


### BREAKING CHANGES

* **map:** `map.jinja` now exports a generic `mapdata` variable
* **map:** The per grain parameter values are now under `TEMPLATE/parameters/`

## [4.3.8](https://github.com/saltstack-formulas/template-formula/compare/v4.3.7...v4.3.8) (2021-02-21)


### Continuous Integration

* **gemfile+lock:** use `ssf` customised `kitchen-docker` repo [skip ci] ([23c2bb2](https://github.com/saltstack-formulas/template-formula/commit/23c2bb2dc26f4c1600d484312a79dd0af0e232d7))
* **kitchen+gitlab-ci:** use latest pre-salted images [skip ci] ([00823a2](https://github.com/saltstack-formulas/template-formula/commit/00823a2d276648d184c92308f7829d0fdeefe0ba))


### Tests

* **_mapdata:** add verification files for Fedora 33 & Tumbleweed ([3347b85](https://github.com/saltstack-formulas/template-formula/commit/3347b85c928cebe8b0c376eae654e67e01730260))

## [4.3.7](https://github.com/saltstack-formulas/template-formula/compare/v4.3.6...v4.3.7) (2021-02-11)


### Continuous Integration

* **pre-commit:** update hook for `rubocop` [skip ci] ([978a7e7](https://github.com/saltstack-formulas/template-formula/commit/978a7e7cd04c00fe6e7b5d113926683a86534094))


### Styles

* **inspec:** match current practices for file and control names ([aa8a58b](https://github.com/saltstack-formulas/template-formula/commit/aa8a58b715fec48b256ff0aa8a0b697b1ae20399))


### Tests

* **share:** standardise with latest changes [skip ci] ([dab2f34](https://github.com/saltstack-formulas/template-formula/commit/dab2f34c587ea6194351c768e9ba141744536607))

## [4.3.6](https://github.com/saltstack-formulas/template-formula/compare/v4.3.5...v4.3.6) (2021-01-14)


### Bug Fixes

* **_mapdata:** ensure map data is directly under `values` ([bcb8e29](https://github.com/saltstack-formulas/template-formula/commit/bcb8e29b687f9804a1cfbda1253da290432cd5b0))


### Tests

* **_mapdata:** update for `_mapdata/init.sls` change ([50162ad](https://github.com/saltstack-formulas/template-formula/commit/50162adad7119285a649321b5f66710974a7983d))

## [4.3.5](https://github.com/saltstack-formulas/template-formula/compare/v4.3.4...v4.3.5) (2020-12-23)


### Code Refactoring

* **map:** use top-level `values:` key in `map.jinja` dumps ([f8e8fcb](https://github.com/saltstack-formulas/template-formula/commit/f8e8fcb29e77d1afded74a2c92789ac8807a4768))

## [4.3.4](https://github.com/saltstack-formulas/template-formula/compare/v4.3.3...v4.3.4) (2020-12-22)


### Continuous Integration

* **commitlint:** ensure `upstream/master` uses main repo URL [skip ci] ([e476d5a](https://github.com/saltstack-formulas/template-formula/commit/e476d5a567d90592ea32f193d2264de59d261711))
* **gitlab-ci:** add `rubocop` linter (with `allow_failure`) [skip ci] ([4c300d0](https://github.com/saltstack-formulas/template-formula/commit/4c300d01cb909f2fbed07d39b22c06198c304cdf))


### Tests

* **_mapdata:** fix existing verification files ([6bbafed](https://github.com/saltstack-formulas/template-formula/commit/6bbafedd1f9ad6e6b659ab6ab4b1736b5c4d9a66))
* **map:** standardise `map.jinja` verification ([4c8cf32](https://github.com/saltstack-formulas/template-formula/commit/4c8cf32db1824fb9841996d758d19c563f5414c5))

## [4.3.3](https://github.com/saltstack-formulas/template-formula/compare/v4.3.2...v4.3.3) (2020-12-16)


### Bug Fixes

* **codeowners:** ensure `lib*` files are owned by `ssf` ([d60cc15](https://github.com/saltstack-formulas/template-formula/commit/d60cc1536637831ef76b2f2c84086b3f88f2684f))


### Continuous Integration

* **gitlab-ci:** use GitLab CI as Travis CI replacement ([0403f62](https://github.com/saltstack-formulas/template-formula/commit/0403f62c7780a8a449617003c5363118a8b6ecd6))

## [4.3.2](https://github.com/saltstack-formulas/template-formula/compare/v4.3.1...v4.3.2) (2020-10-31)


### Bug Fixes

* **convert-formula.sh:** add -_ to allowed chars in formula name ([a999fee](https://github.com/saltstack-formulas/template-formula/commit/a999fee2145d9b0484049808c3c331943580cc3f))
* **convert-formula.sh:** delete all existing tags ([7c33601](https://github.com/saltstack-formulas/template-formula/commit/7c33601fd455df90b1082791cdd282a507334898)), closes [#210](https://github.com/saltstack-formulas/template-formula/issues/210)

## [4.3.1](https://github.com/saltstack-formulas/template-formula/compare/v4.3.0...v4.3.1) (2020-10-28)


### Tests

* **inspec:** `system.rb` must call parent class initialisation ([1ff9ab1](https://github.com/saltstack-formulas/template-formula/commit/1ff9ab15f23ba9f3b78a1b8f9dcef7a062e2b192))

# [4.3.0](https://github.com/saltstack-formulas/template-formula/compare/v4.2.2...v4.3.0) (2020-10-12)


### Continuous Integration

* **pre-commit:** finalise `rstcheck` configuration [skip ci] ([e78aa0c](https://github.com/saltstack-formulas/template-formula/commit/e78aa0cb784752ae699196c6309fe93bf223a306))


### Features

* add Gentoo support ([4c2f4ed](https://github.com/saltstack-formulas/template-formula/commit/4c2f4ede0223e83e1958be33288fa6b83cce7140))

## [4.2.2](https://github.com/saltstack-formulas/template-formula/compare/v4.2.1...v4.2.2) (2020-10-06)


### Bug Fixes

* **commitlint:** fix header length at 72 chars as agreed ([a95061d](https://github.com/saltstack-formulas/template-formula/commit/a95061ddd088210c5111490234bc1588002cddd5))


### Continuous Integration

* **pre-commit:** add to formula [skip ci] ([fd89d62](https://github.com/saltstack-formulas/template-formula/commit/fd89d62ec656dc3e6f84b9834860bf51359452f5))
* **pre-commit:** enable/disable `rstcheck` as relevant [skip ci] ([219e6b7](https://github.com/saltstack-formulas/template-formula/commit/219e6b71c85f06657564c87ba58877cfc5ebe511))

## [4.2.1](https://github.com/saltstack-formulas/template-formula/compare/v4.2.0...v4.2.1) (2020-09-21)


### Continuous Integration

* **kitchen+travis:** use `tiamat` pre-salted images ([3a63304](https://github.com/saltstack-formulas/template-formula/commit/3a63304f13d717fc28efbb06252ffde421ab3621))


### Tests

* **oracle:** add InSpec configuration for `oraclelinux` ([c4b66d8](https://github.com/saltstack-formulas/template-formula/commit/c4b66d8f0b5666261b43ee923565cc516b7fb92f))
* **share:** remove unnecessary hostname mangling ([194aa97](https://github.com/saltstack-formulas/template-formula/commit/194aa97dff47acd59076865489914b4148b1b76d))

# [4.2.0](https://github.com/saltstack-formulas/template-formula/compare/v4.1.1...v4.2.0) (2020-09-04)


### Continuous Integration

* **kitchen:** execute `_madata` state ([31e1096](https://github.com/saltstack-formulas/template-formula/commit/31e1096adda4c23f77b797f35c465ba09043b3a6))
* **kitchen+travis:** fix `centos6` suite and rename to `upstart` ([97309c6](https://github.com/saltstack-formulas/template-formula/commit/97309c6f4d6b18723ec5492564b1344155960ae0))


### Features

* **map:** generate a YAML file to validate `map.jinja` ([fc90075](https://github.com/saltstack-formulas/template-formula/commit/fc90075dd94d874eb283d96259f552812d8a8d82))


### Tests

* **inspec:** share library to access some minion informations ([64c2b6c](https://github.com/saltstack-formulas/template-formula/commit/64c2b6cdae1ad91959b5c0fe67863a529a070428))
* **inspec:** verify `map.jinja` dump ([3dc28bf](https://github.com/saltstack-formulas/template-formula/commit/3dc28bfb3453079deca899352ecdff30daeb42f5))
* **platform_finger:** extract from shared library ([d68ed45](https://github.com/saltstack-formulas/template-formula/commit/d68ed45109aa1274c6bf236db30758d795a3ba2a))

## [4.1.1](https://github.com/saltstack-formulas/template-formula/compare/v4.1.0...v4.1.1) (2020-07-28)


### Continuous Integration

* **kitchen:** use `saltimages` Docker Hub where available [skip ci] ([eab21c3](https://github.com/saltstack-formulas/template-formula/commit/eab21c39fb180d3cf3be93a4ae0678b1fbe6357d))
* **kitchen+travis:** add new platforms [skip ci] ([111a20b](https://github.com/saltstack-formulas/template-formula/commit/111a20b47d89d275ce4ff5213656d6828acb2760))
* **kitchen+travis:** adjust matrix to add `3000.3` [skip ci] ([19ae826](https://github.com/saltstack-formulas/template-formula/commit/19ae82632ece95047b535390bd2325fb30a09af7))
* **travis:** add notifications => zulip [skip ci] ([ac93ad8](https://github.com/saltstack-formulas/template-formula/commit/ac93ad82f143ce9348f841a263df87d717034103))
* **travis:** run linters using `pre-commit` ([6da26cc](https://github.com/saltstack-formulas/template-formula/commit/6da26cca6a3b3ac89137d81b837633358c534396))


### Documentation

* add basic `pre-commit` usage instructions ([c78c068](https://github.com/saltstack-formulas/template-formula/commit/c78c06876eb4c117b3ab00f9da479e8a4c3f1cf5))
* fix whitespace ([d98d98f](https://github.com/saltstack-formulas/template-formula/commit/d98d98f4da1096f4c60c5ec5c15d56d1945c9f50))


### Styles

* **libtofs.jinja:** use Black-inspired Jinja formatting [skip ci] ([55bc69a](https://github.com/saltstack-formulas/template-formula/commit/55bc69a2b194874ceb594c93c8750c320239103c))

# [4.1.0](https://github.com/saltstack-formulas/template-formula/compare/v4.0.9...v4.1.0) (2020-05-12)


### Continuous Integration

* **kitchen+travis:** adjust matrix to add `3000.2` & remove `2018.3` [skip ci] ([efd8797](https://github.com/saltstack-formulas/template-formula/commit/efd8797e66bbe45d58a7155283b6ef47bb3fb7a4))
* **kitchen+travis:** remove `master-py2-arch-base-latest` [skip ci] ([d693f9d](https://github.com/saltstack-formulas/template-formula/commit/d693f9dabf722946a978c64ed4fbfa03653e828c))
* **workflows/commitlint:** add to repo [skip ci] ([574d18f](https://github.com/saltstack-formulas/template-formula/commit/574d18fc2c9628ed142a380aaff3b4c31592bb6f))


### Features

* **convert-formula.sh:** assign `@NONE` as whole-formula owner ([cceffff](https://github.com/saltstack-formulas/template-formula/commit/cceffffef5924b6c156890562e6f64f4872d6867))

## [4.0.9](https://github.com/saltstack-formulas/template-formula/compare/v4.0.8...v4.0.9) (2020-04-25)


### Continuous Integration

* **gemfile.lock:** add to repo with updated `Gemfile` [skip ci] ([d798928](https://github.com/saltstack-formulas/template-formula/commit/d79892867549e13737a2d0f887a1388ec45704af))


### Documentation

* **readme:** show only one level in table of contents ([446b815](https://github.com/saltstack-formulas/template-formula/commit/446b81595822a54792cfbaf23fade20e652d7062))

## [4.0.8](https://github.com/saltstack-formulas/template-formula/compare/v4.0.7...v4.0.8) (2020-04-19)


### Bug Fixes

* **libsaltcli:** update `salt-ssh` detection for `enable_ssh_minions` ([f0e7192](https://github.com/saltstack-formulas/template-formula/commit/f0e7192fb5a546cb0569f9d4257807c8592a00b6))

## [4.0.7](https://github.com/saltstack-formulas/template-formula/compare/v4.0.6...v4.0.7) (2020-04-15)


### Bug Fixes

* **convert-formula.sh:** use portable sed function to make replacements ([41e10b5](https://github.com/saltstack-formulas/template-formula/commit/41e10b5249e0c8827844f438d1995cf7cb42d63a)), closes [#192](https://github.com/saltstack-formulas/template-formula/issues/192)


### Continuous Integration

* **travis:** add quick check that `convert-formula.sh` has worked ([8312063](https://github.com/saltstack-formulas/template-formula/commit/83120632f3a2246ac640155d374634836c34965a))

## [4.0.6](https://github.com/saltstack-formulas/template-formula/compare/v4.0.5...v4.0.6) (2020-04-07)


### Bug Fixes

* **running.sls:** use `watch` not `require` to ensure service restart ([3a1fc35](https://github.com/saltstack-formulas/template-formula/commit/3a1fc35a13f66714cd42583f13679c6f189ae48f))


### Code Refactoring

* **libsaltcli:** use the `opts` dict throughout [skip ci] ([69b632f](https://github.com/saltstack-formulas/template-formula/commit/69b632fbe613d4f99a48f59f64ec93c3897431c8))


### Continuous Integration

* **kitchen+travis:** adjust matrix to add `3000` & remove `2017.7` [skip ci] ([f81c372](https://github.com/saltstack-formulas/template-formula/commit/f81c372dfe12d42139275fc8c9e7aad1b6eec976))
* **kitchen+travis:** adjust matrix to update `3000` to `3000.1` [skip ci] ([f48a727](https://github.com/saltstack-formulas/template-formula/commit/f48a7275644d2baef06adb0d8e74b3c19fd2d8a0))

## [4.0.5](https://github.com/saltstack-formulas/template-formula/compare/v4.0.4...v4.0.5) (2020-03-23)


### Bug Fixes

* **libtofs:** “files_switch” mess up the variable exported by “map.jinja” [skip ci] ([241646f](https://github.com/saltstack-formulas/template-formula/commit/241646fe96447369df00f17ec1c27a53de08bec4))


### Code Refactoring

* **service:** use `systemd-journald` instead of `systemd-udevd` ([a265105](https://github.com/saltstack-formulas/template-formula/commit/a2651058be0d8b09f910aeee2f23703b6cefaa09))

## [4.0.4](https://github.com/saltstack-formulas/template-formula/compare/v4.0.3...v4.0.4) (2020-02-14)


### Bug Fixes

* **libtofs:** “files_switch” mess up the variable defined by “map.jinja” ([ab4ce75](https://github.com/saltstack-formulas/template-formula/commit/ab4ce751a4640303af7acbf7a278aef79b530bb6))


### Continuous Integration

* **kitchen:** avoid using bootstrap for `master` instances ([6ecdb99](https://github.com/saltstack-formulas/template-formula/commit/6ecdb99f83b807b4679dc6534ae425b97eefbe54))

## [4.0.3](https://github.com/saltstack-formulas/template-formula/compare/v4.0.2...v4.0.3) (2020-01-27)


### Bug Fixes

* fix `CentOS Linux-7` and add `os` details from current CI setup ([4be16ca](https://github.com/saltstack-formulas/template-formula/commit/4be16ca4befeddeeb8be1199cd088df7c547523f))
* **travis:** reinstate conversion test [skip ci] ([5d47fda](https://github.com/saltstack-formulas/template-formula/commit/5d47fda1b9f52bff1a4c2cad5097cd3d8cd43521))


### Continuous Integration

* **travis:** use `major.minor` for `semantic-release` version [skip ci] ([e9bfb71](https://github.com/saltstack-formulas/template-formula/commit/e9bfb71fdc0fa80ac63e6ce724f0e5621a4b30ca))

## [4.0.2](https://github.com/saltstack-formulas/template-formula/compare/v4.0.1...v4.0.2) (2019-12-19)


### Bug Fixes

* **convert-formula.sh:** remove "Using this template" post-conversion ([55ab937](https://github.com/saltstack-formulas/template-formula/commit/55ab937c047374fce0548d8c18e8513bc15ead78))
* **convert-formula.sh:** remove `rubocop` override post-conversion ([aca4e44](https://github.com/saltstack-formulas/template-formula/commit/aca4e4428964da745e7b1b7dce15d2c751f76490))
* **convert-formula.sh:** remove CI test post-conversion ([06ec949](https://github.com/saltstack-formulas/template-formula/commit/06ec949fd17bb4b52bb230a6ad2eddfe08a4e693))
* **convert-formula.sh:** reset version to `1.0.0` ([39889ce](https://github.com/saltstack-formulas/template-formula/commit/39889ce303cb57125ba0411ab55266ee018d40e1))


### Documentation

* **convert-formula.sh:** add usage guide ([539a335](https://github.com/saltstack-formulas/template-formula/commit/539a335f8b01ffb3944b742cc2f5852a718546dd))

## [4.0.1](https://github.com/saltstack-formulas/template-formula/compare/v4.0.0...v4.0.1) (2019-12-17)


### Bug Fixes

* **convert-formula.sh:** apply remaining suggestions from [#180](https://github.com/saltstack-formulas/template-formula/issues/180) ([76ecd44](https://github.com/saltstack-formulas/template-formula/commit/76ecd447be66fd9b33ace56836796d3ce24537db)), closes [/github.com/saltstack-formulas/template-formula/pull/180#discussion_r357308821](https://github.com//github.com/saltstack-formulas/template-formula/pull/180/issues/discussion_r357308821) [/github.com/saltstack-formulas/template-formula/pull/180#discussion_r357318860](https://github.com//github.com/saltstack-formulas/template-formula/pull/180/issues/discussion_r357318860) [/github.com/saltstack-formulas/template-formula/pull/180#discussion_r357362707](https://github.com//github.com/saltstack-formulas/template-formula/pull/180/issues/discussion_r357362707)

# [4.0.0](https://github.com/saltstack-formulas/template-formula/compare/v3.3.4...v4.0.0) (2019-12-16)


### Code Refactoring

* improve reusability using an unique keyword TEMPLATE ([2e8ded6](https://github.com/saltstack-formulas/template-formula/commit/2e8ded6565f7bad166323792bf42979aac2980fa))


### Continuous Integration

* **gemfile:** restrict `train` gem version until upstream fix [skip ci] ([1b6164f](https://github.com/saltstack-formulas/template-formula/commit/1b6164fc4a5bda44e8cb1104039606603dab4c2e))
* **travis:** quote pathspecs used with `git ls-files` [skip ci] ([341f495](https://github.com/saltstack-formulas/template-formula/commit/341f495336da0e35d92b3b4acda30f9efa44ec52))


### Features

* add script to ease conversion from template to real formula ([edfa269](https://github.com/saltstack-formulas/template-formula/commit/edfa269e9655407ca26788a8d5564c759abbbb30))


### Tests

* add CI test of conversion script ([7ad85ae](https://github.com/saltstack-formulas/template-formula/commit/7ad85ae0db21888921efabbc88bcafbc65e5bd21))


### BREAKING CHANGES

* changed all state names and ids

## [3.3.4](https://github.com/saltstack-formulas/template-formula/compare/v3.3.3...v3.3.4) (2019-11-27)


### Bug Fixes

* **release.config.js:** use full commit hash in commit link [skip ci] ([4ac8d92](https://github.com/saltstack-formulas/template-formula/commit/4ac8d92778977ed63fe99e4506a2b0a2d41a2bce))


### Continuous Integration

* **kitchen:** use `debian-10-master-py3` instead of `develop` [skip ci] ([14ebf92](https://github.com/saltstack-formulas/template-formula/commit/14ebf928bc07cefa086523e63bed5df7c2879e9b))
* **kitchen:** use `develop` image until `master` is ready (`amazonlinux`) [skip ci] ([42482d7](https://github.com/saltstack-formulas/template-formula/commit/42482d7f9b77f5d34417e25233a9f385075feace))
* **kitchen+travis:** upgrade matrix after `2019.2.2` release [skip ci] ([d0e07b8](https://github.com/saltstack-formulas/template-formula/commit/d0e07b88834f68cc81ce4de34c14a880347fc497))
* **travis:** apply changes from build config validation [skip ci] ([b625245](https://github.com/saltstack-formulas/template-formula/commit/b625245fc62deb6da7cb35de1280ec267718b1cd))
* **travis:** opt-in to `dpl v2` to complete build config validation [skip ci] ([f1fbf7f](https://github.com/saltstack-formulas/template-formula/commit/f1fbf7f620c886827c70fb3970e3b2fac58b8db8))
* **travis:** run `shellcheck` during lint job ([a711665](https://github.com/saltstack-formulas/template-formula/commit/a7116654d875ecb0e7e3e10fc96cbab2e91575f7))
* **travis:** update `salt-lint` config for `v0.0.10` [skip ci] ([faea464](https://github.com/saltstack-formulas/template-formula/commit/faea464f923f552e23a83f28e3192c437f7eabfe))
* **travis:** use build config validation (beta) [skip ci] ([66494bb](https://github.com/saltstack-formulas/template-formula/commit/66494bbc1058adc9ed6fa0074b1c4b6018c4cd48))


### Performance Improvements

* **travis:** improve `salt-lint` invocation [skip ci] ([7a96cd7](https://github.com/saltstack-formulas/template-formula/commit/7a96cd77db71eb8b022df7bd5c1014664124a022))

## [3.3.3](https://github.com/saltstack-formulas/template-formula/compare/v3.3.2...v3.3.3) (2019-10-16)


### Documentation

* **contributing:** add recent `semantic-release` formulas [skip ci] ([](https://github.com/saltstack-formulas/template-formula/commit/e6fb519))
* **contributing:** remove to use org-level file instead [skip ci] ([](https://github.com/saltstack-formulas/template-formula/commit/d2ebccf))
* **readme:** update link to `CONTRIBUTING` [skip ci] ([](https://github.com/saltstack-formulas/template-formula/commit/ed61d09))
* **reamde:** have special notes section ([](https://github.com/saltstack-formulas/template-formula/commit/c68aed5))

## [3.3.2](https://github.com/saltstack-formulas/template-formula/compare/v3.3.1...v3.3.2) (2019-10-08)


### Bug Fixes

* **rubocop:** add fixes using `rubocop --safe-auto-correct` ([484ce24](https://github.com/saltstack-formulas/template-formula/commit/484ce24))
* **rubocop:** fix remaining errors manually ([9566b6f](https://github.com/saltstack-formulas/template-formula/commit/9566b6f))


### Code Refactoring

* **travis:** merge `lint` stage into the `test` stage ([d3b93f8](https://github.com/saltstack-formulas/template-formula/commit/d3b93f8))


### Continuous Integration

* **kitchen:** install required packages to bootstrapped `opensuse` [skip ci] ([1cfed60](https://github.com/saltstack-formulas/template-formula/commit/1cfed60))
* **kitchen:** use bootstrapped `opensuse` images until `2019.2.2` [skip ci] ([0467bdf](https://github.com/saltstack-formulas/template-formula/commit/0467bdf))
* **travis:** quote `${INSTANCE}` when running `kitchen verify` ([00d56a4](https://github.com/saltstack-formulas/template-formula/commit/00d56a4)), closes [/github.com/saltstack-formulas/template-formula/pull/175#discussion_r332525964](https://github.com//github.com/saltstack-formulas/template-formula/pull/175/issues/discussion_r332525964)
* **travis:** run `rubocop` during the `Lint` job ([8d8c766](https://github.com/saltstack-formulas/template-formula/commit/8d8c766))
* **travis:** run `salt-lint` during the `Lint` job ([2df4646](https://github.com/saltstack-formulas/template-formula/commit/2df4646)), closes [/freenode.logbot.info/saltstack-formulas/20191004#c2723464](https://github.com//freenode.logbot.info/saltstack-formulas/20191004/issues/c2723464) [/freenode.logbot.info/saltstack-formulas/20191004#c2724272](https://github.com//freenode.logbot.info/saltstack-formulas/20191004/issues/c2724272)
* **travis:** use `env` and `name` for improved display in Travis ([5f773d1](https://github.com/saltstack-formulas/template-formula/commit/5f773d1)), closes [/github.com/saltstack-formulas/template-formula/pull/175#discussion_r332613933](https://github.com//github.com/saltstack-formulas/template-formula/pull/175/issues/discussion_r332613933)


### Documentation

* **bug_report:** add section requesting commit hash / release tag ([faccb6a](https://github.com/saltstack-formulas/template-formula/commit/faccb6a))
* **bug_report:** group into sections for better logical ordering ([e9b6c2f](https://github.com/saltstack-formulas/template-formula/commit/e9b6c2f))
* **contributing:** add recent `semantic-release` formula ([c2924b0](https://github.com/saltstack-formulas/template-formula/commit/c2924b0))
* **contributing:** add recent `semantic-release` formula ([8d2318c](https://github.com/saltstack-formulas/template-formula/commit/8d2318c))
* **contributing:** add recent `semantic-release` formula [skip ci] ([85118de](https://github.com/saltstack-formulas/template-formula/commit/85118de))
* **issues:** provide `Bug report` & `Feature request` templates ([f90f1f6](https://github.com/saltstack-formulas/template-formula/commit/f90f1f6))
* **issues:** use `Meta` instead of `Optional` as suggested ([65cadb4](https://github.com/saltstack-formulas/template-formula/commit/65cadb4)), closes [/github.com/saltstack-formulas/template-formula/pull/174#issuecomment-538999459](https://github.com//github.com/saltstack-formulas/template-formula/pull/174/issues/issuecomment-538999459)
* **issues:** use larger headings (from level 4 to level 3) ([53e7b75](https://github.com/saltstack-formulas/template-formula/commit/53e7b75))
* **pillar.example:** fix TOFS comment to explain the default path [skip ci] ([fde5063](https://github.com/saltstack-formulas/template-formula/commit/fde5063)), closes [/github.com/saltstack-formulas/libvirt-formula/pull/60#issuecomment-537965254](https://github.com//github.com/saltstack-formulas/libvirt-formula/pull/60/issues/issuecomment-537965254) [/github.com/saltstack-formulas/libvirt-formula/pull/60#issuecomment-537988138](https://github.com//github.com/saltstack-formulas/libvirt-formula/pull/60/issues/issuecomment-537988138)
* **pillar.example:** improve TOFS comment to explain the default path [skip ci] ([27d2fe4](https://github.com/saltstack-formulas/template-formula/commit/27d2fe4)), closes [/github.com/saltstack-formulas/nginx-formula/blob/17291a0ae2c2554707b79d897bb6ddec716e8426/pillar.example#L340-L341](https://github.com//github.com/saltstack-formulas/nginx-formula/blob/17291a0ae2c2554707b79d897bb6ddec716e8426/pillar.example/issues/L340-L341)

## [3.3.1](https://github.com/saltstack-formulas/template-formula/compare/v3.3.0...v3.3.1) (2019-09-23)


### Bug Fixes

* **subcomponent:** clean referencing wrong sls ([394808e](https://github.com/saltstack-formulas/template-formula/commit/394808e))


### Continuous Integration

* use `dist: bionic` & apply `opensuse-leap-15` SCP error workaround ([330b0cb](https://github.com/saltstack-formulas/template-formula/commit/330b0cb))
* **kitchen:** change `log_level` to `debug` instead of `info` ([1b929ff](https://github.com/saltstack-formulas/template-formula/commit/1b929ff))
* **platform:** add `arch-base-latest` ([042e8e2](https://github.com/saltstack-formulas/template-formula/commit/042e8e2))
* **yamllint:** add rule `empty-values` & use new `yaml-files` setting ([70ed7e2](https://github.com/saltstack-formulas/template-formula/commit/70ed7e2)), closes [#164](https://github.com/saltstack-formulas/template-formula/issues/164)


### Documentation

* **contributing:** add recent `semantic-release` formulas ([7f36ae9](https://github.com/saltstack-formulas/template-formula/commit/7f36ae9))

# [3.3.0](https://github.com/saltstack-formulas/template-formula/compare/v3.2.1...v3.3.0) (2019-08-27)


### Bug Fixes

* **libtofs:** avoid using subpath by default ([c07471d](https://github.com/saltstack-formulas/template-formula/commit/c07471d))


### Code Refactoring

* **libtofs:** remove deprecated `v1_path_prefix` argument ([ad2a965](https://github.com/saltstack-formulas/template-formula/commit/ad2a965))


### Features

* **yamllint:** include for this repo and apply rules throughout ([e76525f](https://github.com/saltstack-formulas/template-formula/commit/e76525f))

## [3.2.1](https://github.com/saltstack-formulas/template-formula/compare/v3.2.0...v3.2.1) (2019-08-06)


### Code Refactoring

* **tofs:** move subcomponent definition to `defaults.yaml` ([c269673](https://github.com/saltstack-formulas/template-formula/commit/c269673))
* **tofs:** move subcomponent templates to first `source` match ([70cc92d](https://github.com/saltstack-formulas/template-formula/commit/70cc92d))


### Continuous Integration

* **kitchen+travis:** replace EOL pre-salted images ([42ab22c](https://github.com/saltstack-formulas/template-formula/commit/42ab22c))

# [3.2.0](https://github.com/saltstack-formulas/template-formula/compare/v3.1.1...v3.2.0) (2019-08-03)


### Bug Fixes

* **formula:** update to current oldest supported version of Salt ([878eca1](https://github.com/saltstack-formulas/template-formula/commit/878eca1))


### Documentation

* **libtofs:** explain usage of sub-directory for components ([42a75d9](https://github.com/saltstack-formulas/template-formula/commit/42a75d9))
* **readme:** describe the new “template.subcomponent” states ([6b595cd](https://github.com/saltstack-formulas/template-formula/commit/6b595cd))


### Features

* **sub-component:** manage a dedicated configuration file ([c4440d7](https://github.com/saltstack-formulas/template-formula/commit/c4440d7))
* **tofs:** lookup files directory in “tpldir” hierarchy ([5c495fb](https://github.com/saltstack-formulas/template-formula/commit/5c495fb))


### Tests

* **inspec:** verify subcomponent configuration file ([fd55e03](https://github.com/saltstack-formulas/template-formula/commit/fd55e03))

## [3.1.1](https://github.com/saltstack-formulas/template-formula/compare/v3.1.0...v3.1.1) (2019-07-25)


### Bug Fixes

* **tofs:** prepend the config-based `source_files` to the default ([3483e76](https://github.com/saltstack-formulas/template-formula/commit/3483e76)), closes [/github.com/saltstack-formulas/nginx-formula/pull/247#issuecomment-514262549](https://github.com//github.com/saltstack-formulas/nginx-formula/pull/247/issues/issuecomment-514262549) [#151](https://github.com/saltstack-formulas/template-formula/issues/151)


### Documentation

* **tofs:** ensure merged will all recent changes ([6a614d9](https://github.com/saltstack-formulas/template-formula/commit/6a614d9))
* **tofs:** update from `nginx-formula` ([23a221e](https://github.com/saltstack-formulas/template-formula/commit/23a221e)), closes [/github.com/saltstack-formulas/nginx-formula/pull/238#discussion_r289124365](https://github.com//github.com/saltstack-formulas/nginx-formula/pull/238/issues/discussion_r289124365)

# [3.1.0](https://github.com/saltstack-formulas/template-formula/compare/v3.0.9...v3.1.0) (2019-07-24)


### Bug Fixes

* **grain:** fix grain value ([26edfa0](https://github.com/saltstack-formulas/template-formula/commit/26edfa0))


### Documentation

* **map:** update comments in `os*.yaml` after adding `osarchmap` ([d71a258](https://github.com/saltstack-formulas/template-formula/commit/d71a258))


### Features

* **mapping:** introduce osarchmap per issue [#13](https://github.com/saltstack-formulas/template-formula/issues/13) ([41ac40d](https://github.com/saltstack-formulas/template-formula/commit/41ac40d))


### Tests

* **osarch:** add unit test for osarch ([1be2052](https://github.com/saltstack-formulas/template-formula/commit/1be2052))

## [3.0.9](https://github.com/saltstack-formulas/template-formula/compare/v3.0.8...v3.0.9) (2019-07-24)


### Bug Fixes

* **libtofs:** don't crash if “tofs.files_switch” lookup a list ([0979d35](https://github.com/saltstack-formulas/template-formula/commit/0979d35))


### Documentation

* **contributing:** add recent `semantic-release` formula ([f9def86](https://github.com/saltstack-formulas/template-formula/commit/f9def86))
* **contributing:** add recent `semantic-release` formula ([ed8c55a](https://github.com/saltstack-formulas/template-formula/commit/ed8c55a))
* **contributing:** add recent `semantic-release` formulas ([57d0b85](https://github.com/saltstack-formulas/template-formula/commit/57d0b85))


### Tests

* **libtofs:** “tofs.files_switch” lookup can return a list ([13f1728](https://github.com/saltstack-formulas/template-formula/commit/13f1728))

## [3.0.8](https://github.com/saltstack-formulas/template-formula/compare/v3.0.7...v3.0.8) (2019-07-08)


### Documentation

* **contributing:** add template-formula to `semantic-release` formulas ([87e4ebc](https://github.com/saltstack-formulas/template-formula/commit/87e4ebc))

## [3.0.7](https://github.com/saltstack-formulas/template-formula/compare/v3.0.6...v3.0.7) (2019-07-04)


### Documentation

* **contributing:** add recent `semantic-release` formula ([c679cb5](https://github.com/saltstack-formulas/template-formula/commit/c679cb5))

## [3.0.6](https://github.com/saltstack-formulas/template-formula/compare/v3.0.5...v3.0.6) (2019-06-28)


### Code Refactoring

* **string:** remove capitalisation from 'template' string ([7062210](https://github.com/saltstack-formulas/template-formula/commit/7062210))

## [3.0.5](https://github.com/saltstack-formulas/template-formula/compare/v3.0.4...v3.0.5) (2019-06-28)


### Documentation

* **contributing:** add recent `semantic-release` formula ([fc50a9e](https://github.com/saltstack-formulas/template-formula/commit/fc50a9e))

## [3.0.4](https://github.com/saltstack-formulas/template-formula/compare/v3.0.3...v3.0.4) (2019-06-27)


### Documentation

* **contributing:** add recent `semantic-release` formulas ([22052fc](https://github.com/saltstack-formulas/template-formula/commit/22052fc))

## [3.0.3](https://github.com/saltstack-formulas/template-formula/compare/v3.0.2...v3.0.3) (2019-06-25)


### Documentation

* **contributing:** add recent `semantic-release` formula ([7f56237](https://github.com/saltstack-formulas/template-formula/commit/7f56237))

## [3.0.2](https://github.com/saltstack-formulas/template-formula/compare/v3.0.1...v3.0.2) (2019-06-20)


### Documentation

* **contributing:** add recent `semantic-release` formulas ([461c7a5](https://github.com/saltstack-formulas/template-formula/commit/461c7a5))

## [3.0.1](https://github.com/saltstack-formulas/template-formula/compare/v3.0.0...v3.0.1) (2019-06-16)


### Tests

* **inspec:** readme for default profile & os-name depreciated ([3fa7bce](https://github.com/saltstack-formulas/template-formula/commit/3fa7bce))

# [3.0.0](https://github.com/saltstack-formulas/template-formula/compare/v2.2.1...v3.0.0) (2019-06-13)


### Code Refactoring

* **pkgname:** reserve 'pkg' as packaging dict ([c6ae81c](https://github.com/saltstack-formulas/template-formula/commit/c6ae81c))


### Continuous Integration

* **kitchen+travis:** modify matrix to include `develop` platform ([7b5d4ff](https://github.com/saltstack-formulas/template-formula/commit/7b5d4ff))


### BREAKING CHANGES

* **pkgname:** the parameter `pkg` is now a dictionary. References
 to `template.pkg` should be changed to `template.pkg.name`.

## [2.2.1](https://github.com/saltstack-formulas/template-formula/compare/v2.2.0...v2.2.1) (2019-05-31)


### Code Refactoring

* **`osfamilymap`:** avoid *BSD ambiguity with MacOS `rootgroup` ([3338605](https://github.com/saltstack-formulas/template-formula/commit/3338605))

# [2.2.0](https://github.com/saltstack-formulas/template-formula/compare/v2.1.18...v2.2.0) (2019-05-31)


### Features

* **macos:** basic package and group handling ([8c3fe22](https://github.com/saltstack-formulas/template-formula/commit/8c3fe22))

## [2.1.18](https://github.com/saltstack-formulas/template-formula/compare/v2.1.17...v2.1.18) (2019-05-29)


### Bug Fixes

* **`libtofs`:** use `select` to deal with empty strings in path ([afe0751](https://github.com/saltstack-formulas/template-formula/commit/afe0751))
* **`libtofs`:** use `strip` to deal with leading/trailing slashes ([2563a46](https://github.com/saltstack-formulas/template-formula/commit/2563a46))

## [2.1.17](https://github.com/saltstack-formulas/template-formula/compare/v2.1.16...v2.1.17) (2019-05-27)


### Continuous Integration

* **kitchen:** add Bundler binstub for Kitchen ([7bb7c53](https://github.com/saltstack-formulas/template-formula/commit/7bb7c53))


### Documentation

* **readme:** tidy headings ([d931ed1](https://github.com/saltstack-formulas/template-formula/commit/d931ed1))

## [2.1.16](https://github.com/saltstack-formulas/template-formula/compare/v2.1.15...v2.1.16) (2019-05-27)


### Documentation

* **contributing:** add ufw formula to semantic release formulas ([18ff689](https://github.com/saltstack-formulas/template-formula/commit/18ff689))

## [2.1.15](https://github.com/saltstack-formulas/template-formula/compare/v2.1.14...v2.1.15) (2019-05-25)


### Tests

* **`services_spec`:** remove temporary `suse` conditional ([00d4a77](https://github.com/saltstack-formulas/template-formula/commit/00d4a77))

## [2.1.14](https://github.com/saltstack-formulas/template-formula/compare/v2.1.13...v2.1.14) (2019-05-25)


### Bug Fixes

* **`config/file`:** add missing space before Jinja `}}` ([5cd08ab](https://github.com/saltstack-formulas/template-formula/commit/5cd08ab))

## [2.1.13](https://github.com/saltstack-formulas/template-formula/compare/v2.1.12...v2.1.13) (2019-05-24)


### Documentation

* **readme:** add testing requirements section (from `vault-formula`) ([e04413e](https://github.com/saltstack-formulas/template-formula/commit/e04413e))

## [2.1.12](https://github.com/saltstack-formulas/template-formula/compare/v2.1.11...v2.1.12) (2019-05-24)


### Continuous Integration

* **travis:** improve recommended matrix usage comment ([b08a0fd](https://github.com/saltstack-formulas/template-formula/commit/b08a0fd))
* **travis:** reduce matrix down to 6 instances (ref: [#118](https://github.com/saltstack-formulas/template-formula/issues/118)) ([a8834e2](https://github.com/saltstack-formulas/template-formula/commit/a8834e2))


### Documentation

* **contributing:** add `bind-formula` to `semantic-release` formulas ([3da78b0](https://github.com/saltstack-formulas/template-formula/commit/3da78b0))

## [2.1.11](https://github.com/saltstack-formulas/template-formula/compare/v2.1.10...v2.1.11) (2019-05-18)


### Documentation

* **contributing:** add recent `semantic-release` formula ([486b393](https://github.com/saltstack-formulas/template-formula/commit/486b393))

## [2.1.10](https://github.com/saltstack-formulas/template-formula/compare/v2.1.9...v2.1.10) (2019-05-16)


### Documentation

* **contributing:** fix link to contributing docs ([b6a33d3](https://github.com/saltstack-formulas/template-formula/commit/b6a33d3))

## [2.1.9](https://github.com/saltstack-formulas/template-formula/compare/v2.1.8...v2.1.9) (2019-05-16)


### Documentation

* move contributing sections and links to ease adaptation ([741896d](https://github.com/saltstack-formulas/template-formula/commit/741896d))

## [2.1.8](https://github.com/saltstack-formulas/template-formula/compare/v2.1.7...v2.1.8) (2019-05-16)


### Documentation

* **contributing:** add recent `semantic-release` formulas ([#110](https://github.com/saltstack-formulas/template-formula/issues/110)) ([ab7afd4](https://github.com/saltstack-formulas/template-formula/commit/ab7afd4))

## [2.1.7](https://github.com/saltstack-formulas/template-formula/compare/v2.1.6...v2.1.7) (2019-05-15)


### Styles

* **indent:** fix indentation ([34d1307](https://github.com/saltstack-formulas/template-formula/commit/34d1307))

## [2.1.6](https://github.com/saltstack-formulas/template-formula/compare/v2.1.5...v2.1.6) (2019-05-15)


### Bug Fixes

* **`map.jinja`:** _merge_ defaults and `config.get` ([91bc2f0](https://github.com/saltstack-formulas/template-formula/commit/91bc2f0))

## [2.1.5](https://github.com/saltstack-formulas/template-formula/compare/v2.1.4...v2.1.5) (2019-05-15)


### Bug Fixes

* **`map.jinja`:** use tplroot ([b9c5e03](https://github.com/saltstack-formulas/template-formula/commit/b9c5e03))

## [2.1.4](https://github.com/saltstack-formulas/template-formula/compare/v2.1.3...v2.1.4) (2019-05-15)


### Bug Fixes

* **`map.jinja`:** remove `merge` from `config.get` (for `salt-ssh`) ([00e474c](https://github.com/saltstack-formulas/template-formula/commit/00e474c)), closes [#95](https://github.com/saltstack-formulas/template-formula/issues/95)

## [2.1.3](https://github.com/saltstack-formulas/template-formula/compare/v2.1.2...v2.1.3) (2019-05-13)


### Bug Fixes

* **travis:** don't install gems twice ([925d8e2](https://github.com/saltstack-formulas/template-formula/commit/925d8e2))


### Documentation

* **readme:** add testing section based on `postgres-formula` ([c309d5f](https://github.com/saltstack-formulas/template-formula/commit/c309d5f))

## [2.1.2](https://github.com/saltstack-formulas/template-formula/compare/v2.1.1...v2.1.2) (2019-05-13)


### Bug Fixes

* **gitignore:** add Gemfile.lock to .gitignore ([87fa410](https://github.com/saltstack-formulas/template-formula/commit/87fa410))

## [2.1.1](https://github.com/saltstack-formulas/template-formula/compare/v2.1.0...v2.1.1) (2019-05-13)


### Documentation

* **semantic-release:** add list of semantic-release compatible formulas ([97b19b9](https://github.com/saltstack-formulas/template-formula/commit/97b19b9))

# [2.1.0](https://github.com/saltstack-formulas/template-formula/compare/v2.0.6...v2.1.0) (2019-05-12)


### Features

* **centos-6:** reshape formula and tests for this platform ([a4b1608](https://github.com/saltstack-formulas/template-formula/commit/a4b1608)), closes [#104](https://github.com/saltstack-formulas/template-formula/issues/104)

## [2.0.6](https://github.com/saltstack-formulas/template-formula/compare/v2.0.5...v2.0.6) (2019-05-02)


### Continuous Integration

* **kitchen+travis:** use latest pre-salted images ([91ef13b](https://github.com/saltstack-formulas/template-formula/commit/91ef13b))


### Tests

* **inspec:** disable `service`-based tests for `opensuse-leap-15` ([848c2ad](https://github.com/saltstack-formulas/template-formula/commit/848c2ad))

## [2.0.5](https://github.com/saltstack-formulas/template-formula/compare/v2.0.4...v2.0.5) (2019-04-30)


### Documentation

* **tofs:** remove whitespace from blank line ([0881b7d](https://github.com/saltstack-formulas/template-formula/commit/0881b7d))

## [2.0.4](https://github.com/saltstack-formulas/template-formula/compare/v2.0.3...v2.0.4) (2019-04-27)


### Code Refactoring

* **map:** use `config.get` instead of `pillar.get` ([5dc0b86](https://github.com/saltstack-formulas/template-formula/commit/5dc0b86))


### Continuous Integration

* **gemfile:** update `kitchen-salt` version ([ad31c32](https://github.com/saltstack-formulas/template-formula/commit/ad31c32))

## [2.0.3](https://github.com/saltstack-formulas/template-formula/compare/v2.0.2...v2.0.3) (2019-04-24)


### Bug Fixes

* **comments:** explain that at least an empty dict is required ([426f955](https://github.com/saltstack-formulas/template-formula/commit/426f955)), closes [#93](https://github.com/saltstack-formulas/template-formula/issues/93)


### Continuous Integration

* **kitchen:** use pre-salted images instead ([2855ed6](https://github.com/saltstack-formulas/template-formula/commit/2855ed6))

## [2.0.2](https://github.com/saltstack-formulas/template-formula/compare/v2.0.1...v2.0.2) (2019-04-22)


### Code Refactoring

* **config_clean:** remove unused import from `libtofs.jinja` ([b7cb585](https://github.com/saltstack-formulas/template-formula/commit/b7cb585))


### Continuous Integration

* **kitchen+travis:** implement new distro-python-salt_version matrix ([bd4792d](https://github.com/saltstack-formulas/template-formula/commit/bd4792d))

## [2.0.1](https://github.com/saltstack-formulas/template-formula/compare/v2.0.0...v2.0.1) (2019-03-25)


### Code Refactoring

* **tofs:** ensure (v2 > v1 > default) checking for `src_files` ([3e62d7b](https://github.com/saltstack-formulas/template-formula/commit/3e62d7b))
* **tofs:** make `files_switch` macro fully portable ([a98b777](https://github.com/saltstack-formulas/template-formula/commit/a98b777))
* **tofs:** use `config` rather than `pillar` throughout ([5730e94](https://github.com/saltstack-formulas/template-formula/commit/5730e94))

# [2.0.0](https://github.com/saltstack-formulas/template-formula/compare/v1.2.6...v2.0.0) (2019-03-24)


### Code Refactoring

* **tofs:** move “files_switch” macro to “libtofs.jinja” ([da7e692](https://github.com/saltstack-formulas/template-formula/commit/da7e692))


### BREAKING CHANGES

* **tofs:** every formula writer will need to change the import
to use this new version.

* template/libtofs.jinja: provides the “files_switch” macro.

* docs/TOFS_pattern.rst: update documentation to use the new path.

* template/config/clean.sls: change import from “macros.jinja” to “libtofs.jinja”.

* template/config/file.sls: ditoo.

## [1.2.6](https://github.com/saltstack-formulas/template-formula/compare/v1.2.5...v1.2.6) (2019-03-24)


### Reverts

* **kitchen+travis:** use `debian:jessie-backports` as `debian-8` ([dcd141a](https://github.com/saltstack-formulas/template-formula/commit/dcd141a)), closes [/github.com/saltstack/salt-pack/issues/657#issuecomment-474954298](https://github.com//github.com/saltstack/salt-pack/issues/657/issues/issuecomment-474954298)

## [1.2.5](https://github.com/saltstack-formulas/template-formula/compare/v1.2.4...v1.2.5) (2019-03-23)


### Bug Fixes

* **travis:** use version numbers in Gemfile to prevent failed builds ([35f7111](https://github.com/saltstack-formulas/template-formula/commit/35f7111))

## [1.2.4](https://github.com/saltstack-formulas/template-formula/compare/v1.2.3...v1.2.4) (2019-03-22)


### Code Refactoring

* **tofs:** avoid using “salt['config.get']” for formula writers ([60d43e7](https://github.com/saltstack-formulas/template-formula/commit/60d43e7))

## [1.2.3](https://github.com/saltstack-formulas/template-formula/compare/v1.2.2...v1.2.3) (2019-03-13)


### Documentation

* **tofs:** incorrect path for “source_files” lookup key ([a76f659](https://github.com/saltstack-formulas/template-formula/commit/a76f659))

## [1.2.2](https://github.com/saltstack-formulas/template-formula/compare/v1.2.1...v1.2.2) (2019-03-09)


### Bug Fixes

* **tofs:** update use of state ID in `config` and `pillar` ([3d9a24c](https://github.com/saltstack-formulas/template-formula/commit/3d9a24c))
* **tofs:** use `source_files` instead of `files` ([5110716](https://github.com/saltstack-formulas/template-formula/commit/5110716)), closes [/freenode.logbot.info/saltstack-formulas/20190308#c2046753](https://github.com//freenode.logbot.info/saltstack-formulas/20190308/issues/c2046753)

## [1.2.1](https://github.com/saltstack-formulas/template-formula/compare/v1.2.0...v1.2.1) (2019-03-07)


### Code Refactoring

* **kitchen:** `pillars-from-files` => `pillars_from_files` ([7c954a7](https://github.com/saltstack-formulas/template-formula/commit/7c954a7)), closes [/github.com/saltstack-formulas/packages-formula/pull/50#discussion_r262769817](https://github.com//github.com/saltstack-formulas/packages-formula/pull/50/issues/discussion_r262769817)


### Styles

* **map:** use `-` for each Jinja block ([64e3834](https://github.com/saltstack-formulas/template-formula/commit/64e3834))

# [1.2.0](https://github.com/saltstack-formulas/template-formula/compare/v1.1.2...v1.2.0) (2019-03-03)


### Features

* **m2r:** use `m2r` to convert automatic `.md` files to `.rst` ([b86ddf4](https://github.com/saltstack-formulas/template-formula/commit/b86ddf4))

## [1.1.2](https://github.com/saltstack-formulas/template-formula/compare/v1.1.1...v1.1.2) (2019-03-03)


### Documentation

* **contributing:** add documentation contribution guidelines ([dff0ee8](https://github.com/saltstack-formulas/template-formula/commit/dff0ee8))
* **rtd:** add comment to CSS file for overriding in-use Sphinx theme ([f237364](https://github.com/saltstack-formulas/template-formula/commit/f237364))
* **rtd:** clean up numerous issues and inconsistencies ([ad5a8b8](https://github.com/saltstack-formulas/template-formula/commit/ad5a8b8))
* **tofs:** use `literalinclude` of `macros.jinja` instead of code dupe ([3f0071b](https://github.com/saltstack-formulas/template-formula/commit/3f0071b))

## [1.1.1](https://github.com/saltstack-formulas/template-formula/compare/v1.1.0...v1.1.1) (2019-03-01)


### Continuous Integration

* **travis:** remove obsolete `markdown-toc` process ([97fbb60](https://github.com/saltstack-formulas/template-formula/commit/97fbb60))


### Documentation

* **contributing:** add TOC to match all other pages ([7b1a2a9](https://github.com/saltstack-formulas/template-formula/commit/7b1a2a9))
* **readme:** add Read the Docs build status badge ([f47797d](https://github.com/saltstack-formulas/template-formula/commit/f47797d))
* **tofs:** replace existing `.md` with `.rst` and add to RTD ([fd68168](https://github.com/saltstack-formulas/template-formula/commit/fd68168))
* **tofs:** use table to list authorship ([2f0e20f](https://github.com/saltstack-formulas/template-formula/commit/2f0e20f))

# [1.1.0](https://github.com/saltstack-formulas/template-formula/compare/v1.0.1...v1.1.0) (2019-03-01)


### Documentation

* **rtd:** add basic `docs/conf.py` to allow additional customisation ([18d3924](https://github.com/saltstack-formulas/template-formula/commit/18d3924))


### Features

* **rtd:** provide custom CSS file for overriding in-use Sphinx theme ([24bd338](https://github.com/saltstack-formulas/template-formula/commit/24bd338))

## [1.0.1](https://github.com/saltstack-formulas/template-formula/compare/v1.0.0...v1.0.1) (2019-03-01)


### Continuous Integration

* **travis:** remove unavailable files from `markdown-toc` process ([3148f0d](https://github.com/saltstack-formulas/template-formula/commit/3148f0d))


### Documentation

* **contributing:** convert to `.rst` and move to `docs` subdir ([474f318](https://github.com/saltstack-formulas/template-formula/commit/474f318))
* **index:** add `CONTRIBUTING` to the `toctree` ([0c98e67](https://github.com/saltstack-formulas/template-formula/commit/0c98e67))
* **readme:** move under `docs` subdir to access in both GitHub and RTD ([c92f674](https://github.com/saltstack-formulas/template-formula/commit/c92f674))
* **readme:** update heading markers for consistency ([5a2bea8](https://github.com/saltstack-formulas/template-formula/commit/5a2bea8))
* **rtd:** add basic `index.rst` to allow RTD to produce docs ([f02139f](https://github.com/saltstack-formulas/template-formula/commit/f02139f))
* **rtd:** use internal link targets at the top of each `.rst` file ([da09528](https://github.com/saltstack-formulas/template-formula/commit/da09528))

# [1.0.0](https://github.com/saltstack-formulas/template-formula/compare/v0.7.6...v1.0.0) (2019-02-28)


### Code Refactoring

* **components:** split components into separate subdirs ([d957055](https://github.com/saltstack-formulas/template-formula/commit/d957055)), closes [/github.com/saltstack-formulas/template-formula/pull/48#pullrequestreview-207182085](https://github.com//github.com/saltstack-formulas/template-formula/pull/48/issues/pullrequestreview-207182085) [/github.com/saltstack-formulas/template-formula/pull/48#discussion_r259805312](https://github.com//github.com/saltstack-formulas/template-formula/pull/48/issues/discussion_r259805312)
* **include+require:** use variable for duplicate values ([4443518](https://github.com/saltstack-formulas/template-formula/commit/4443518))
* **pkg:** change to `package` instead ([2cd82e5](https://github.com/saltstack-formulas/template-formula/commit/2cd82e5)), closes [/github.com/saltstack-formulas/template-formula/pull/48#discussion_r259951123](https://github.com//github.com/saltstack-formulas/template-formula/pull/48/issues/discussion_r259951123)
* **pkg:** move `pkg` related components into separate directory ([c21f82b](https://github.com/saltstack-formulas/template-formula/commit/c21f82b))
* **states:** set state IDs based on a dependable structure ([6690ee6](https://github.com/saltstack-formulas/template-formula/commit/6690ee6)), closes [/github.com/saltstack-formulas/template-formula/pull/48#discussion_r259953473](https://github.com//github.com/saltstack-formulas/template-formula/pull/48/issues/discussion_r259953473) [/github.com/saltstack-formulas/template-formula/pull/48#discussion_r259956996](https://github.com//github.com/saltstack-formulas/template-formula/pull/48/issues/discussion_r259956996)
* **topdir:** use for `include` and `require` except `init.sls` ([a218e91](https://github.com/saltstack-formulas/template-formula/commit/a218e91))
* **tpldir:** use `topdir` globally in place of `tpldir` ([2838bc9](https://github.com/saltstack-formulas/template-formula/commit/2838bc9))
* **tplroot:** use `tplroot` instead of `topdir` to match `tpldata` ([b7356b0](https://github.com/saltstack-formulas/template-formula/commit/b7356b0))


### Continuous Integration

* **kitchen:** specify `image` explicitly for each platform ([b25fbdc](https://github.com/saltstack-formulas/template-formula/commit/b25fbdc))
* **kitchen+travis:** use `debian:jessie-backports` as `debian-8` ([1b9d249](https://github.com/saltstack-formulas/template-formula/commit/1b9d249)), closes [#50](https://github.com/saltstack-formulas/template-formula/issues/50) [/github.com/saltstack/salt-pack/issues/657#issuecomment-467932962](https://github.com//github.com/saltstack/salt-pack/issues/657/issues/issuecomment-467932962)


### Documentation

* **components:** update for separation of `pkg`, `config` & `service` ([726fcab](https://github.com/saltstack-formulas/template-formula/commit/726fcab))
* **readme:** add suggested improvement to `template.service.clean` ([bf1039c](https://github.com/saltstack-formulas/template-formula/commit/bf1039c))
* **readme:** fix typos ([007159a](https://github.com/saltstack-formulas/template-formula/commit/007159a))


### Features

* **pkg:** add `clean` states ([422c7ac](https://github.com/saltstack-formulas/template-formula/commit/422c7ac))
* **pkg:** use `require` requisite between `pkg` states ([6e7141b](https://github.com/saltstack-formulas/template-formula/commit/6e7141b)), closes [/github.com/saltstack/salt/blob/0c78d7dc894058988d171a28a11bd4a9dbf60266/salt/utils/jinja.py#L120](https://github.com//github.com/saltstack/salt/blob/0c78d7dc894058988d171a28a11bd4a9dbf60266/salt/utils/jinja.py/issues/L120) [/github.com/saltstack/salt/blob/0c78d7dc894058988d171a28a11bd4a9dbf60266/salt/utils/templates.py#L145](https://github.com//github.com/saltstack/salt/blob/0c78d7dc894058988d171a28a11bd4a9dbf60266/salt/utils/templates.py/issues/L145) [/github.com/saltstack/salt/issues/10838#issuecomment-391718086](https://github.com//github.com/saltstack/salt/issues/10838/issues/issuecomment-391718086)


### Reverts

* **kitchen+travis:** disable `debian-8` due to `2019.2` bug ([e8f0f7e](https://github.com/saltstack-formulas/template-formula/commit/e8f0f7e))


### BREAKING CHANGES

* **states:** Wholesale state ID changes will break implementations
that are relying on the previous state IDs for requisite purposes.
* **pkg:** Changing the `pkg` directory to `package` will break
implementations that are depending on `pkg` for `include` or `sls`-based
requisite purposes.

## [0.7.6](https://github.com/saltstack-formulas/template-formula/compare/v0.7.5...v0.7.6) (2019-02-27)


### Documentation

* **yaml:** os*.yaml map files needs at least an empty dict ([dd99750](https://github.com/saltstack-formulas/template-formula/commit/dd99750))

## [0.7.5](https://github.com/saltstack-formulas/template-formula/compare/v0.7.4...v0.7.5) (2019-02-27)


### Bug Fixes

* **pillar:** fix `os_family` typo ([3f89c12](https://github.com/saltstack-formulas/template-formula/commit/3f89c12))
* **tofs:** update comments in `files_switch` macro for new method ([3fa3640](https://github.com/saltstack-formulas/template-formula/commit/3fa3640))


### Code Refactoring

* **macros:** use `tplroot` instead of `topdir` to match `tpldata` ([923b459](https://github.com/saltstack-formulas/template-formula/commit/923b459))


### Documentation

* **tofs:** add more sub-headings to ease document navigation ([2c5dc21](https://github.com/saltstack-formulas/template-formula/commit/2c5dc21))
* **tofs:** apply language formatting to source code blocks ([0638413](https://github.com/saltstack-formulas/template-formula/commit/0638413))
* **tofs:** explain how all parts of the `source` can be customised ([2f82eb5](https://github.com/saltstack-formulas/template-formula/commit/2f82eb5)), closes [#44](https://github.com/saltstack-formulas/template-formula/issues/44)
* **tofs:** improve general use of language ([5105d29](https://github.com/saltstack-formulas/template-formula/commit/5105d29))
* **tofs:** update the `files_switch` section for the updated macro ([788f732](https://github.com/saltstack-formulas/template-formula/commit/788f732))
* **tofs:** use `{%-` for all Jinja statements ([4348df8](https://github.com/saltstack-formulas/template-formula/commit/4348df8))

## [0.7.4](https://github.com/saltstack-formulas/template-formula/compare/v0.7.3...v0.7.4) (2019-02-27)


### Continuous Integration

* **kitchen:** check for repos updates before trying package installation ([b632383](https://github.com/saltstack-formulas/template-formula/commit/b632383))
* **kitchen+travis:** disable `debian-8` due to `2019.2` installation bug ([178c710](https://github.com/saltstack-formulas/template-formula/commit/178c710))


### Documentation

* **contributing:** separate `BREAKING CHANGE` under its own heading ([ee053d7](https://github.com/saltstack-formulas/template-formula/commit/ee053d7))

## [0.7.3](https://github.com/saltstack-formulas/template-formula/compare/v0.7.2...v0.7.3) (2019-02-25)


### Bug Fixes

* **tofs:** use `tpldir` derivative `topdir` for pillar (config) paths ([5e9df00](https://github.com/saltstack-formulas/template-formula/commit/5e9df00))

## [0.7.2](https://github.com/saltstack-formulas/template-formula/compare/v0.7.1...v0.7.2) (2019-02-24)


### Code Refactoring

* **tpldir:** use `tpldir` or derivatives to make formula portable ([52d03d8](https://github.com/saltstack-formulas/template-formula/commit/52d03d8)), closes [#22](https://github.com/saltstack-formulas/template-formula/issues/22)


### Continuous Integration

* **kitchen:** improve comments about `opensuse` problems encountered ([c246939](https://github.com/saltstack-formulas/template-formula/commit/c246939))
* **travis:** prevent `release` stage running for PRs ([3a072c7](https://github.com/saltstack-formulas/template-formula/commit/3a072c7)), closes [/travis-ci.com/saltstack-formulas/template-formula/jobs/180068519#L466](https://github.com//travis-ci.com/saltstack-formulas/template-formula/jobs/180068519/issues/L466) [/github.com/saltstack-formulas/template-formula/pull/42#issuecomment-466446324](https://github.com//github.com/saltstack-formulas/template-formula/pull/42/issues/issuecomment-466446324)

## [0.7.1](https://github.com/saltstack-formulas/template-formula/compare/v0.7.0...v0.7.1) (2019-02-24)


### Continuous Integration

* **kitchen:** use `salt-minion` version of `opensuse` to ensure tests run ([99b073a](https://github.com/saltstack-formulas/template-formula/commit/99b073a))


### Documentation

* **changelog:** remove erroneous "closes" used by `semantic-release` ([be4571d](https://github.com/saltstack-formulas/template-formula/commit/be4571d))

# [0.7.0](https://github.com/saltstack-formulas/template-formula/compare/v0.6.0...v0.7.0) (2019-02-23)


### Features

* **tofs:** implement backwards-compatible TOFSv2 for configurability ([068a94d](https://github.com/saltstack-formulas/template-formula/commit/068a94d))

# [0.6.0](https://github.com/saltstack-formulas/template-formula/compare/v0.5.0...v0.6.0) (2019-02-23)


### Documentation

* **contributing:** add basic introductory text before the TOC ([45ccaf6](https://github.com/saltstack-formulas/template-formula/commit/45ccaf6))
* **contributing:** modify quoted heading to prevent TOC inclusion ([abcb6ef](https://github.com/saltstack-formulas/template-formula/commit/abcb6ef))
* **readme:** convert note into a heading ([5f2d789](https://github.com/saltstack-formulas/template-formula/commit/5f2d789))


### Features

* **toc:** use `markdown-toc` directly to update inline ([a5bae1e](https://github.com/saltstack-formulas/template-formula/commit/a5bae1e))

# [0.5.0](https://github.com/saltstack-formulas/template-formula/compare/v0.4.0...v0.5.0) (2019-02-23)


### Features

* **kitchen+travis:** add `opensuse-leap` after resolving issues ([7614a3c](https://github.com/saltstack-formulas/template-formula/commit/7614a3c))
* **kitchen+travis:** conduct tests on a wider range of platforms ([1348078](https://github.com/saltstack-formulas/template-formula/commit/1348078))


### Tests

* **inspec:** update `supports` for all platforms added ([42f93b3](https://github.com/saltstack-formulas/template-formula/commit/42f93b3))

# [0.4.0](https://github.com/saltstack-formulas/template-formula/compare/v0.3.6...v0.4.0) (2019-02-23)


### Documentation

* **contributing:** centre-align version bump columns in table ([a238cae](https://github.com/saltstack-formulas/template-formula/commit/a238cae))


### Features

* **authors:** update automatically alongside `semantic-release` ([8000098](https://github.com/saltstack-formulas/template-formula/commit/8000098))

## [0.3.6](https://github.com/saltstack-formulas/template-formula/compare/v0.3.5...v0.3.6) (2019-02-22)


### Continuous Integration

* **travis:** include `commitlint` stage ([6659a69](https://github.com/saltstack-formulas/template-formula/commit/6659a69))
* **travis:** remove obsolete check based on `$TRAVIS_TEST_RESULT` ([6df9c95](https://github.com/saltstack-formulas/template-formula/commit/6df9c95))


### Documentation

* **contributing:** update with sub-headings and `commitlint` details ([ea2c9a4](https://github.com/saltstack-formulas/template-formula/commit/ea2c9a4))

## [0.3.5](https://github.com/saltstack-formulas/template-formula/compare/v0.3.4...v0.3.5) (2019-02-21)


### Code Refactoring

* **kitchen:** prefer `kitchen.yml` to `.kitchen.yml` ([3860bf9](https://github.com/saltstack-formulas/template-formula/commit/3860bf9))

## [0.3.4](https://github.com/saltstack-formulas/template-formula/compare/v0.3.3...v0.3.4) (2019-02-21)


### Documentation

* **contributing:** add commit message formatting instructions ([fb3d173](https://github.com/saltstack-formulas/template-formula/commit/fb3d173))

## [0.3.3](https://github.com/saltstack-formulas/template-formula/compare/v0.3.2...v0.3.3) (2019-02-20)


### Documentation

* **changelog:** add missing entry under `v0.3.2` ([50352b5](https://github.com/saltstack-formulas/template-formula/commit/50352b5))

## [0.3.2](https://github.com/saltstack-formulas/template-formula/compare/v0.3.1...v0.3.2) (2019-02-20)


### Documentation

* **README:** remove gitchangelog ([2fc85fc](https://github.com/saltstack-formulas/template-formula/commit/2fc85fc))
* **contributing:** create blank template ([3633e8f](https://github.com/saltstack-formulas/template-formula/commit/3633e8f))

## [0.3.1](https://github.com/saltstack-formulas/template-formula/compare/v0.3.0...v0.3.1) (2019-02-20)


### Documentation

* **changelog:** merge previous `rst` into new `md` format ([2b4e485](https://github.com/saltstack-formulas/template-formula/commit/2b4e485))

# [0.3.0](https://github.com/saltstack-formulas/template-formula/compare/v0.2.0...v0.3.0) (2019-02-20)


### Features

* **semantic-release:** configure for this formula ([cbcfd75](https://github.com/saltstack-formulas/template-formula/commit/cbcfd75))

# [0.2.0](https://github.com/saltstack-formulas/template-formula/compare/v0.1.7...v0.2.0) (2019-02-17)

* Added a working testing scaffold and travis support. [Javier Bértoli]

## [0.1.7](https://github.com/saltstack-formulas/template-formula/compare/v0.1.6...v0.1.7) (2019-02-16)

### Fix

* Typo in the installation instructions. [Niels Abspoel]

### Other

* Update the changelog. [Niels Abspoel]
* Update README with link to install gitchangelog [Imran Iqbal]

## [0.1.6](https://github.com/saltstack-formulas/template-formula/compare/v0.1.5...v0.1.6) (2019-02-16)

* Add changelog generator. [Niels Abspoel]

## [0.1.5](https://github.com/saltstack-formulas/template-formula/compare/v0.1.4...v0.1.5) (2019-02-15)

* Prepare v0.1.5 [Imran Iqbal]
* Fix missing ')' [gmazrael]

## [0.1.4](https://github.com/saltstack-formulas/template-formula/compare/v0.1.3...v0.1.4) (2019-02-15)

* Replace obsolete VERSION file and replace with FORMULA file. [Imran Iqbal]

## [0.1.3](https://github.com/saltstack-formulas/template-formula/compare/v0.1.2...v0.1.3) (2019-02-12)

* Updated changelog and version. [Alexander Weidinger]
* Map.jinja: use grains.filter\_by instead of defaults.merge. [Alexander Weidinger]

    because defaults.merge does not work with salt-ssh. <https://github.com/saltstack/salt/issues/51605>

    Added osfingermap.yaml.

## [0.1.2](https://github.com/saltstack-formulas/template-formula/compare/v0.1.1...v0.1.2) (2019-02-12)

* Improve comments and examples in osfamilymap & osmap [Imran Iqbal]
* Fix map.jinja and add more OSes. [Imran Iqbal]

## [0.1.1](https://github.com/saltstack-formulas/template-formula/compare/v0.1.0...v0.1.1) (2019-02-10)

* Update. [Niels Abspoel]
* Update formula with map.jinja and style guide references, improve README and VERSION. [Niels Abspoel]

# [0.1.0](https://github.com/saltstack-formulas/template-formula/compare/v0.0.9...v0.1.0) (2019-02-10)

* Examples must be consistent. [Daniel Dehennin]

    The “template” is kept during rendering.

    * TOFS\_pattern.md: add “template” to rendered state.
    * template/macros.jinja: ditoo.

* Remove double slash in generated salt URL. [Daniel Dehennin]

    When the files are “full path” with leading slash “/”, the generated URL contain a double slash because of the join.

    * template/macros.jinja: remove leading slash before joining parts.
    * TOFS\_pattern.md: mirror changes of “macros.jinja”.

* Add an example for “ntp” of the use of “files\_switch” [Daniel Dehennin]
* Accept pillar separator in “files\_switch” prefix. [Daniel Dehennin]

    The prefix was used for 2 purposes:

    * define the pillar prefix where to lookup “:files\_switch”. It supports the colon “:” separator to lookup in pillar subtree like “foo:bar”
    * define the path prefix where to look for “files/”, It did not support separator to lookup inside directory tree.

    This patch only replace any colon “:” with “/” when looking up “files/” directory, with the “foo:bar” prefix:

    * lookup “foo:bar:files\_switch” pillar to get list of grains to match
    * lookup files under “salt://foo/bar/files/”
    * TOFS\_pattern.md: document the new use of “prefix” supporting colon “:”.
    * template/macros.jinja: transform any colon “:” in “prefix” by slash
    “/” to lookup files.

* Make TOFS pattern example usable. [Daniel Dehennin]

    The example could not be used as-is. This commit improve conformity to formula conventions.

    * TOFS\_pattern.md: add missing commas “,” in “map.jinja” and extra one
    to ease the addition of new entries. Import “map.jinja” in “init.sls” and “conf.sls”. Declare descriptive state IDs. Use the “module.function” notation. Use the “name” parameter.

* Cosmetics modification of TOFS pattern documentation. [Daniel Dehennin]
    * TOFS\_pattern.md: add myself as modifier.
    Trim trailing whitespaces. Separate titles from first paragraph.

* Switch template.config to TOFS pattern. [Daniel Dehennin]
* Import TOFS pattern from Zabbix formula. [Daniel Dehennin]

## [0.0.9](https://github.com/saltstack-formulas/template-formula/compare/v0.0.8...v0.0.9) (2019-02-10)

* Add VERSION file. [Karim Hamza]
* Add note about formula versioning. [Karim Hamza]

## [0.0.8](https://github.com/saltstack-formulas/template-formula/compare/v0.0.7...v0.0.8) (2019-02-10)

* Align with SaltStack official formulas doc page. [Denys Havrysh]
* Use https in the link to SaltStack documentation. [Denys Havrysh]

## [0.0.7](https://github.com/saltstack-formulas/template-formula/compare/v0.0.6...v0.0.7) (2019-02-10)

* Map.ninja: fix typos and leftover comments. [Marco Molteni]
* Remove whitespace in map.jinja comment. [Andrew Gabbitas]

## [0.0.6](https://github.com/saltstack-formulas/template-formula/compare/v0.0.5...v0.0.6) (2019-02-10)

* Improve style and jinja too match salt-formula. [Niels Abspoel]
* Propose new-ish formula style - defaults live in defaults.yml - map jinja overrides by grain + merges pillar:lookup - split all contextually similar states in their own files. [puneet kandhari]

## [0.0.5](https://github.com/saltstack-formulas/template-formula/compare/v0.0.4...v0.0.5) (2019-02-10)

* Change states to use short-dec style. [Seth House]
* Update CHANGELOG.rst. [Nitin Madhok]
* Update README.rst. [Nitin Madhok]

    Fix broken link
* Fixing pillar to match the map file. [Forrest]

    Map file and pillar didn't match.

## [0.0.4](https://github.com/saltstack-formulas/template-formula/compare/v0.0.3...v0.0.4) (2019-02-10)

* Add change log. [Antti Jokipii]

## [0.0.3](https://github.com/saltstack-formulas/template-formula/compare/v0.0.2...v0.0.3) (2019-02-10)

* Updated the license and readme to match our standards. [Forrest Alvarez]
* Use map.jinja content in init.sls. [Eugene Vereschagin]
* Add map.jinja. [Eugene Vereschagin]

## [0.0.2](https://github.com/saltstack-formulas/template-formula/compare/v0.0.1...v0.0.2) (2019-02-10)

* Add link to Salt Formula documentation. [Eugene Vereschagin]
* Change extension from .md to .rst. [Eugene Vereschagin]

## [0.0.1](https://github.com/saltstack-formulas/template-formula/releases/tag/v0.0.1) (2019-02-10)

* Initial commit. [Lukas Erlacher]
