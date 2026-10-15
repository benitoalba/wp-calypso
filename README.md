# Domain postcode formatting demo

Screenshots for Automattic/wp-calypso issue #72345.

The local demo renders the actual `ManagedContactDetailsFormFields` component and address inputs with controlled contact data. The before bundle uses upstream commit `2b7681d1d115f2e68c1933270b0d4932d6074803`; the after bundle uses the postcode formatting fix. Both use the existing postal-code formatter.

Country data is supplied locally. Network queries, the phone input, and the unused Google Workspace branch are omitted from the demo. This is a component demo, not a live checkout session.

- `before.png`: UK input `sw1a1aa` remains lowercase after Tab.
- `after.png`: UK input becomes `SW1A 1AA`; trimming the city preserves the postcode.
- `after-canada.png`: Canadian input becomes `K1A 0B1`.
- `after-mobile.png`: UK formatting on a 390-pixel-wide viewport.

Browser assertions passed for UK and Canadian lowercase postcodes, surrounding whitespace, city trimming, empty and whitespace-only values, US ZIP+4 and five-digit ZIP codes, and mobile keyboard blur. Both viewports fit without horizontal overflow. No uncaught browser exceptions occurred. React reports an existing Organization notice DOM nesting warning in both versions.
