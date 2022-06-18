# @nhost/vue

## 0.3.0

### Minor Changes

- 6f0a3005: `sendMfaOtp` now returns a promise
  When using `useSignInEmailPassword`, the `sendMfaOtp` was `void`. It now returns a promise that resolves when the server returned the result of the OTP code submission, and returns `isSuccess`, `isError`, and `error`.

### Patch Changes

- Updated dependencies [6f0a3005]
- Updated dependencies [6f0a3005]
  - @nhost/nhost-js@1.4.0
  - @nhost/core@0.7.1

## 0.2.1

### Patch Changes

- 6f45856c: Correct use of ref values in action options
  The `nestedUnref` helper was not correctly un-refing nested values. For instance, the values the properties of the following metadata were still `refs`:

  ```jsx
  const { signUpEmailPassword } = useSignUpEmailPassword()
  const firstName = ref('John')
  const lastName = ref('Doe')
  signUpEmailPassword((email: 'john@world.com'), (password: 'not-1234'), {
    metadata: { firstName, lastName }
  })
  ```

## 0.2.0

### Minor Changes

- c1613394: Deanonymisation
  Once signed in anonymously, users can deanonymise using `nhost.auth.deanonymize`.
  Deanonymisation works the same way as email+password sign-up or passwordless sign-in. The related methods, hooks in React and composables in Vue can therefore be used for deanonymising users, such as `nhost.auth.signUp`, `useSignUpEmailPassword`, and `useSignInEmailPasswordless`.

### Patch Changes

- Updated dependencies [c1613394]
  - @nhost/core@0.7.0
  - @nhost/nhost-js@1.3.0

## 0.1.6

### Patch Changes

- Updated dependencies [08a37aae]
  - @nhost/core@0.6.5
  - @nhost/nhost-js@1.2.4

## 0.1.5

### Patch Changes

- ebad0936: reverted ESM related changes
- Updated dependencies [ebad0936]
  - @nhost/core@0.6.4
  - @nhost/nhost-js@1.2.3

## 0.1.4

### Patch Changes

- 1b37b9f6: fix: ESM import path fixes
- Updated dependencies [1b37b9f6]
  - @nhost/core@0.6.3
  - @nhost/nhost-js@1.2.2

## 0.1.3

### Patch Changes

- 78341491: fix: Next.js and React issues with ESM packages
  chore: Updated output bundle names
- Updated dependencies [78341491]
  - @nhost/core@0.6.2
  - @nhost/nhost-js@1.2.1

## 0.1.2

### Patch Changes

- bc11c9e5: chore: Changed copy script to support Windows
  fix: Fixed warnings about unknown globals occurring while building the packages
- 2b2f8e91: fix: ESM related issues in Node environments
  chore: Improved the way different formats are exposed via `exports` field in package.js
- Updated dependencies [bc11c9e5]
- Updated dependencies [2b2f8e91]
- Updated dependencies [858014e4]
  - @nhost/core@0.6.1
  - @nhost/nhost-js@1.2.0

## 0.1.0

### Minor Changes

- 7c8f0926: new `@nhost/vue` library
  This package brings a similar logic as `@nhost/react` and `@nhost/nextjs` to the Vue 3 framework. It comes with an Nhost client that is installed as a Vue plugin, composables, and integration with `vue-router` and `vue-apollo`.

### Patch Changes

- 7c8f0926: use the [same methods and typings](https://github.com/nhost/nhost/tree/feat/vue/packages/core/src/promises) to interact with xstate machines in both `@nhost/hasura-auth-js`, `@nhost/react` hooks and `@nhost/vue` composables
  Both `@nhost/react`, `@nhost/hasura-auth-js` and `@nhost/vue` interact with the authentication state in a similar way. As a result, the same code was repeated three times, with risks of insonsistency and difficult maintainability. `@nhost/core` now contains the logic and Typescript interfaces that are used in the Vanilla client, React hooks and Vue composables.
- Updated dependencies [7c8f0926]
- Updated dependencies [7c8f0926]
- Updated dependencies [7c8f0926]
  - @nhost/core@0.6.0
  - @nhost/nhost-js@1.1.14
