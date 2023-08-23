## API Report File for "@backstage/frontend-plugin-api"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts
import { ComponentType } from 'react';

// @public (undocumented)
export type AnyExtensionDataMap = Record<string, ExtensionDataRef<any>>;

// @public (undocumented)
export interface BackstagePlugin {
  // (undocumented)
  $$type: 'backstage-plugin';
  // (undocumented)
  defaultExtensionInstances: ExtensionInstanceConfig[];
  // (undocumented)
  id: string;
}

// @public (undocumented)
export interface BackstagePluginOptions {
  // (undocumented)
  defaultExtensionInstances?: ExtensionInstanceConfig[];
  // (undocumented)
  id: string;
}

// @public (undocumented)
export const coreExtensionData: {
  reactComponent: ExtensionDataRef<ComponentType<{}>>;
  routePath: ExtensionDataRef<string>;
};

// @public (undocumented)
export function createExtension<
  TData extends AnyExtensionDataMap,
  TPoint extends Record<
    string,
    {
      extensionData: AnyExtensionDataMap;
    }
  >,
>(options: CreateExtensionOptions<TData, TPoint>): Extension;

// @public (undocumented)
export interface CreateExtensionOptions<
  TData extends AnyExtensionDataMap,
  TPoint extends Record<
    string,
    {
      extensionData: AnyExtensionDataMap;
    }
  >,
> {
  // (undocumented)
  factory(options: {
    bind: ExtensionDataBind<TData>;
    config?: unknown;
    inputs: {
      [pointName in keyof TPoint]: ExtensionDataValue<
        TPoint[pointName]['extensionData']
      >[];
    };
  }): void;
  // (undocumented)
  inputs?: TPoint;
  // (undocumented)
  output: TData;
}

// @public (undocumented)
export function createPlugin(options: BackstagePluginOptions): BackstagePlugin;

// @public (undocumented)
export interface Extension {
  // (undocumented)
  $$type: 'extension';
  // (undocumented)
  factory(options: {
    bind: ExtensionDataBind<AnyExtensionDataMap>;
    config?: unknown;
    inputs: Record<string, Array<Record<string, unknown>>>;
  }): void;
  // (undocumented)
  inputs: Record<
    string,
    {
      extensionData: AnyExtensionDataMap;
    }
  >;
  // (undocumented)
  output: AnyExtensionDataMap;
}

// @public (undocumented)
export type ExtensionDataBind<TData extends AnyExtensionDataMap> = {
  [K in keyof TData]: (value: TData[K]['T']) => void;
};

// @public (undocumented)
export type ExtensionDataRef<T> = {
  id: string;
  T: T;
  $$type: 'extension-data';
};

// @public (undocumented)
export type ExtensionDataValue<TData extends AnyExtensionDataMap> = {
  [K in keyof TData]: TData[K]['T'];
};

// @public (undocumented)
export interface ExtensionInstanceConfig {
  // (undocumented)
  at: string;
  // (undocumented)
  config: unknown;
  // (undocumented)
  extension: Extension;
  // (undocumented)
  id: string;
}
```