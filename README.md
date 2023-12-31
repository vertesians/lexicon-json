# Lexicon Json

This repository offers the lexicon of New Ithkuil in json format based on the
http://ithkuil.net/newithkuil_lexicon.pdf.

Currently it does not include the affixes like `-řst` but is planned in the
future.

## Format

```ts
type Specs = {
  /** basic */
  "BSC": string;
  /** contential */
  "CTE": string;
  /** constitutive */
  "CSV": string;
  /** objective */
  "OBJ": string;
};

type Root = {
  root: string;
  refers?: string;
  stems?: [
    Specs | string,
    Specs | string,
    Specs | string,
  ];
  /** Notes in markdown format */
  notes?: string;
  /** See the root below if the stems are empty as they may have similar rules */
  see?: string;
}[];

type Lexicon = Array<Root>;
```

## Progress

### Roots

|           | Roots |
| --------- | ----- |
| Chapter 1 | ✅    |
| Chapter 2 | ✅    |
| Chapter 3 | ✅    |
| Chapter 4 | ✅    |
| Chapter 5 | ✅    |
| Chapter 6 | ✅    |
| Chapter 7 | ✅    |

### Affixes

Planned after [Enthrirhs](https://github.com/yuorb/enthrirhs) released v0.2.0.

## Scripts

### `json`

```console
$ deno task json
```

Generate a minified json file to `output/lexicon.json`, which includes all the
roots.

### `yaml`

```console
$ deno task yaml
```

Generate a yaml file to `output/lexicon.yaml`, which includes all the roots.
