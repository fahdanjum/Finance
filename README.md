## Fixed-Income Risk Engine

A Python project for building and understanding fixed-income valuation and
interest-rate risk analytics using Government of Canada market data.

The goal of this project is to implement the underlying mechanics directly,
rather than relying on pre-built bond pricing or risk functions.

## Current Version — V1

The current model:
- Imports Government of Canada yield data using the Valet API. 
- Constructs a yield curve from available market tenors
- Uses linear interpolation for intermediate maturities
- Generates discount factors
- Prices a vanilla fixed-rate bond from its cash flows
- Calculates Macaulay and estimates Modified Duration
- Estimates DV01

## Example

For a $1,000 face-value, 5-year bond with a 3% annual coupon, the model
produced approximately:

Bond Price: $973
DV01: $0.44 per 1 bp

Based on Oct 2, 2026 Bank of Canada selected bond yield data. 

## Current Simplifications

Version 1 intentionally makes several simplifying assumptions:

- Annual coupon payments
- Linear yield interpolation
- Government of Canada quoted yields are used directly in constructing
  the discount curve
- No accrued-interest / clean-price treatment
- ModDur calculated using interpolated curve output in place of optimized YTM.

These assumptions will be refined as the project develops.

## Planned Development

- Semi-annual and configurable coupon frequencies
- Portfolio-level valuation and DV01
- Key-rate DV01
- Nelson-Siegel-Svensson curve fitting
   
## Purpose

This is a learning project focused on developing a practical understanding
of fixed-income valuation, yield-curve construction, and interest-rate risk.
