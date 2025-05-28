# BEAST2 Galaxy Tools

This repository contains Galaxy tool wrappers for BEAST2 (Bayesian Evolutionary Analysis Sampling Trees).

## Overview

BEAST2 is a cross-platform program for Bayesian MCMC analysis of molecular sequences. It estimates rooted, time-measured phylogenies using strict or relaxed molecular clock models.

## Tools Included

### BEAST2 Main Analysis
- **Tool ID**: `beast2`
- **Function**: Run Bayesian phylogenetic MCMC analysis
- **Inputs**: 
  - BEAST2 XML configuration file OR
  - Sequence alignment (NEXUS, FASTA, PHYLIP formats)
- **Outputs**:
  - Parameter log file (.log)
  - Trees file (.trees) 
  - Screen output log
  - State file (for resuming runs)

## Installation

This tool requires the `beast2` conda package, which is automatically installed when you install the tool from the Galaxy ToolShed.

## Usage

### Option 1: Pre-configured XML
1. Create a BEAST2 XML file using BEAUti (BEAST2's GUI)
2. Upload the XML file to Galaxy
3. Run the BEAST2 tool with your XML file

### Option 2: Automatic XML Generation
1. Upload your sequence alignment (NEXUS, FASTA, or PHYLIP format)
2. Configure analysis parameters in the tool form:
   - Chain length (number of MCMC steps)
   - Sample frequency 
   - Substitution model (JC69, HKY, GTR, TN93)
   - Clock model (strict, relaxed lognormal, relaxed exponential)
   - Tree prior (coalescent, Yule, birth-death)
3. Run the analysis

## Test Data

The `test-data/` directory contains:
- `test_simple.xml`: Example BEAST2 configuration file
- `test_simple.log`: Expected log output 
- `test_simple.trees`: Expected trees output

## Requirements

- Galaxy 22.01 or later
- BEAST2 v2.7.7 (installed via conda)

## Citation

If you use this tool, please cite:

> Bouckaert R, Vaughan TG, Barido-Sottani J, Duchêne S, Fourment M, Gavryushkina A, et al. 
> BEAST 2.5: An advanced software platform for Bayesian evolutionary analysis. 
> PLoS computational biology. 2019;15(4):e1006650.

## License

This Galaxy tool wrapper is released under the MIT License.
BEAST2 itself is released under the GNU Lesser General Public License v2.1.

## Support

For issues with this Galaxy tool wrapper, please open an issue on the Galaxy ToolShed.
For BEAST2 software issues, please visit: https://github.com/CompEvol/beast2/issues

## Version History

- v2.7.7+galaxy0: Initial release with BEAST2 v2.7.7
  - Support for XML input and automatic XML generation
  - Basic substitution models (JC69, HKY)
  - Strict and relaxed clock models
  - Standard tree priors