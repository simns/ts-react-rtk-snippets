# Typescript + React + Redux Toolkit Snippets

These are a selection of snippets that I use keeping in mind modern trends with React development. Relevant snippets are meant to be used only with Typescript, functional components, and hooks.

These snippets are also for Redux Toolkit specifically.

## Snippets

<!-- prettier-ignore -->
| Prefix                | Description                                                |
|-----------------------|------------------------------------------------------------|
| rfc                   | React Functional Component (no props)                      |
| rfcp                  | React Functional Component with Props                      |
| rus                   | React useState                                             |
| rusb                  | React useState boolean                                     |
| russ                  | React useState string                                      |
| rusa                  | React useState Array                                       |
| rusn                  | React useState number                                      |
| rue                   | React useEffect                                            |
| rur                   | React useRef                                               |
| ruc                   | React useContext                                           |
| rcc                   | React createContext                                        |
| rfcroutes             | Functional Component with Routes                           |
| exd                   | export default                                             |
| ext                   | export type                                                |
| exi                   | export interface                                           |
| exe                   | export enum                                                |
| exes                  | export enum as strings                                     |
| rtkslice              | Redux Toolkit Slice                                        |
| rtkaction             | Redux Toolkit Slice action                                 |
| rtkuad                | Redux Toolkit useAppDispatch                               |
| rtkuas                | Redux Toolkit useAppSelector                               |
| imp-rtkhooks          | Redux Toolkit import dispatch and selector hooks           |
| rtkthunk              | Redux Toolkit basic createAsyncThunk                       |
| rtkasync              | Redux Toolkit basic createAsyncThunk                       |
| rtkthunk-state        | Redux Toolkit createAsyncThunk with getState               |
| rtkasync-state        | Redux Toolkit createAsyncThunk with getState               |
| rtkthunk-custom       | Redux Toolkit custom params createAsyncThunk               |
| rtkasync-custom       | Redux Toolkit custom params createAsyncThunk               |
| rtkthunk-custom-state | Redux Toolkit custom params createAsyncThunk with getState |
| rtkasync-custom-state | Redux Toolkit custom params createAsyncThunk with getState |
| rtk-extred-thunk      | Redux Toolkit extraReducers for async thunk                |
| rtk-extred-action     | Redux Toolkit extraReducers for separate slice action      |

## Expanded code

`rfc` - React Functional Component (no props)

```tsx
const |: React.FC = () => {
  return <div>|</div>;
};

export default |;
```

`rfcp` - React Functional Component with Props

```tsx
type Props = {
  |
};

const |: React.FC<Props> = (props) => {
  const { | } = props;

  return <div>|</div>;
};

export default |;
```

`rus` - React useState

Note: these useState snippets will auto-camelCase the `set__` method after pressing Tab.

```ts
const [|, set|] = useState<|>(|);
```

`rusb` - React useState boolean

```ts
const [|, set|] = useState<boolean>(false);
```

`russ` - React useState string

```ts
const [|, set|] = useState<string>("");
```

`rusa` - React useState Array

```ts
const [|, set|] = useState<Array<|>>([]);
```

`rusn` - React useState number

```ts
const [|, set|] = useState<number>(0);
```

`rue` - React useEffect

```ts
useEffect(() => {
  |
}, [|]);
```

`rur` - React useRef

Note: The `HTMLDivElement` is default but the snippet will highlight it to be changed freely.

```ts
const |Ref = useRef<HTMLDivElement>(null);
```

`ruc` - React useContext

```ts
const | = useContext(|Context);
```

`rcc` - React createContext

```ts
const |Context = createContext<|>(|);
```

`rfcroutes` - Functional Component with Routes

```tsx
import { BrowserRouter, Route, Routes } from "react-router-dom";

const |: React.FC = () => {
  return (
    <BrowserRouter>
      <Routes>
        <Route element={<| />} path="/|" />
      </Routes>
    </BrowserRouter>
  );
};

export default |;
```

`exd` - export default

```ts
export default |;
```

`ext` - export type

```ts
export type | = {
  |
};
```

`exi` - export interface

```ts
export interface | {
  |
}
```

`exe` - export enum

```ts
export enum | {
  |,
  |
}
```

`exes` - export enum as string

```ts
export enum | {
  | = "|",
  | = "|",
  | = "|",
  | = "|"
}
```

`rtkslice` - Redux Toolkit Slice

Note: This snippet is complex. The name entered for the `type __State` is used in various places in the Slice and is auto-cased. The first property in that type will be turned into the first reducer action as well.

```ts
import { createSlice, PayloadAction } from "@reduxjs/toolkit";

type |State = {
  |: |;
};

const initialState: |State = {
  |: |
};

export const | = createSlice({
  name: "|",
  initialState,
  reducers: {
    set|: (state, action: PayloadAction<|>) => {
      state.| = action.payload;
    },
  }
});

export const { reducer: |Reducer } = |;
export const { set| } = |.actions;
```

`rtkaction` - Redux Toolkit Slice action

```ts
|: (state, action: PayloadAction<|>) => {
  state.|
}
```

`rtkuad` - Redux Toolkit useAppDispatch

```ts
const dispatch = useAppDispatch();
```

`rtkuas` - Redux Toolkit useAppSelector

```ts
const | = useAppSelector((state: RootState) => state.|);
```

`imp-rtkhooks` - Redux Toolkit import dispatch and selector hooks

Note: The value of `@/store/hooks` is what I use and is default here, but the snippet will highlight it for you to change freely.

```ts
import { useAppDispatch, useAppSelector } from "@/store/hooks";
```

`rtkthunk`,`rtkasync` - Redux Toolkit basic createAsyncThunk

```ts
export const | = createAsyncThunk<void, void>(
  "|",
  async (_, { dispatch }) => {
    |
  }
);
```

`rtkthunk-state`,`rtkasync-state` - Redux Toolkit createAsyncThunk with getState

```ts
export const | = createAsyncThunk<void, void, { state: RootState }>(
  "|",
  async (_, { dispatch, getState }) => {
    const state = getState();

    |
  }
);
```

`rtkthunk-custom`,`rtkasync-custom` - Redux Toolkit custom params createAsyncThunk

```ts
export const | = createAsyncThunk<ReturnType, ParamType>(
  "|",
  async (|, { dispatch }) => {
    |
  }
);
```

`rtkthunk-custom-state`,`rtkasync-custom-state` - Redux Toolkit custom params createAsyncThunk with getState

```ts
export const | = createAsyncThunk<ReturnType, ParamType, { state: RootState }>(
  "|",
  async (|, { dispatch, getState }) => {
    const state = getState();

    |
  }
);
```

`rtk-extred-thunk` - Redux Toolkit extraReducers for async thunk

```ts
extraReducers: (builder) => {
  builder.addCase(|.pending, (state, action) => {
    // Pending action
  });
  builder.addCase(|.rejected, (state, action) => {
    // Rejected action
  });
  builder.addCase(|.fulfilled, (state, action) => {
    // Fulfilled action
  });
}
```

`rtk-extred-action` - Redux Toolkit extraReducers for separate slice action

```ts
extraReducers: (builder) => {
  builder.addCase(|, (state, action) => {
    |
  });
}
```
