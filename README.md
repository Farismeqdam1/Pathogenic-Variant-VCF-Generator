# Pathogenic Variant VCF Generator

A web-based tool for generating VCF (Variant Call Format) files with pathogenic variant annotations for research, testing, and educational purposes.

## Overview

The VCF Generator allows researchers, clinicians, and students to create properly formatted VCF files containing pathogenic variants. The tool generates standard VCF v4.3 format files with comprehensive metadata headers and clinical annotations.

## Features

- **Interactive Web Interface**: Easy-to-use form for inputting variant data
- **Complete VCF v4.3 Compliance**: Generates properly formatted files following VCF standards
- **Pathogenic Variant Focus**: Specialized fields for clinical significance and disease associations
- **HGVS Annotation Support**: Input fields for both protein and cDNA nomenclature
- **Flexible Chromosome Selection**: Supports autosomes (1-22), sex chromosomes (X, Y), and mitochondrial (MT)
- **Download Functionality**: Direct download of generated VCF files
- **Pre-filled Example**: BRCA1 pathogenic variant example for demonstration

## Usage

### Basic Workflow

1. **Open the HTML file** in a web browser
2. **Fill in variant information**:
   - Select chromosome from dropdown
   - Enter genomic position
   - Specify reference and alternative alleles
   - Add gene name and clinical annotations
3. **Click "Generate VCF File"** to create the formatted output
4. **Download** the generated VCF file using the download button

### Input Fields

#### Required Fields
- **Chromosome**: Select from chr1-22, chrX, chrY, chrMT
- **Position**: Genomic coordinate (positive integer)
- **Reference Allele**: Original nucleotide(s) at the position
- **Alternative Allele**: Variant nucleotide(s)
- **Gene Name**: Associated gene symbol
- **Clinical Significance**: Pathogenic classification
- **Sample Name**: Identifier for the sample
- **Genotype**: Zygosity information (0/0, 0/1, 1/1)

#### Optional Fields
- **Variant ID**: dbSNP rsID or custom identifier
- **Quality Score**: Variant calling quality score
- **HGVS Protein Change**: Protein-level variant description
- **HGVS cDNA Change**: Coding DNA variant description
- **Disease Association**: Related disease or syndrome

### Example Usage

The tool comes pre-populated with a BRCA1 pathogenic variant example:
- Chromosome: chr17
- Position: 43094692
- Reference: A
- Alternative: G
- Gene: BRCA1
- HGVS Protein: p.Cys61Gly
- Disease: Hereditary breast and ovarian cancer syndrome

## Output Format

Generated VCF files include:

### Header Section
- File format declaration (VCFv4.3)
- Creation date
- Reference genome (GRCh38)
- INFO field definitions
- FORMAT field definitions
- FILTER definitions
- Contig information

### Data Section
- Column headers (#CHROM, POS, ID, REF, ALT, QUAL, FILTER, INFO, FORMAT, SAMPLE)
- Variant data line with all specified annotations

### Sample INFO Fields
- `GENEINFO`: Gene name
- `CLNSIG`: Clinical significance
- `HGVSP`: HGVS protein change
- `HGVSC`: HGVS coding sequence change
- `CLNDN`: Disease name
- `AF`: Allele frequency (estimated)
- `DP`: Depth of coverage (estimated)

## File Structure

```
├── index.html          # Main application file
├── README.md           # This documentation
└── generated/          # Downloaded VCF files (created by browser)
```

## Requirements

### Browser Compatibility
- Modern web browsers supporting HTML5, CSS3, and ES6 JavaScript
- Tested on: Chrome 90+, Firefox 88+, Safari 14+, Edge 90+

### No Installation Required
- Pure client-side application
- No server dependencies
- No external libraries required

## Technical Details

### VCF Format Compliance
- Follows VCF v4.3 specification
- Includes mandatory header lines
- Properly formatted INFO and FORMAT fields
- Tab-separated values in data lines

### Validation
- Required field validation
- Nucleotide sequence validation (A, T, C, G only)
- Positive integer validation for genomic positions
- Chromosome format standardization

### Data Processing
- Automatic uppercase conversion for alleles
- Default values for optional fields (represented as ".")
- Date formatting for file headers
- Sanitization of text inputs for VCF compatibility

## Limitations

### Current Limitations
- Single variant per file generation
- No support for structural variants
- Limited to basic genotype formats (GT:DP:GQ)
- No real-time validation against genome references
- Client-side only (no database integration)

### Intended Use
- Educational and research purposes
- Testing and development workflows
- Prototype variant file creation
- Not intended for clinical diagnostic use

## Examples

### Common Pathogenic Variants You Can Generate

**TP53 (Li-Fraumeni syndrome)**
- Chromosome: chr17
- Position: 7577121
- Ref: C → Alt: T
- Gene: TP53

**CFTR (Cystic Fibrosis)**
- Chromosome: chr7
- Position: 117559593
- Ref: CTT → Alt: C
- Gene: CFTR

**APOE (Alzheimer's disease risk)**
- Chromosome: chr19
- Position: 45411941
- Ref: T → Alt: C
- Gene: APOE

## Troubleshooting

### Common Issues

**File won't download**
- Check browser popup blocker settings
- Ensure browser supports HTML5 download attribute

**Invalid VCF format**
- Verify all required fields are filled
- Check that alleles contain only A, T, C, G characters
- Ensure position is a positive integer

**Missing clinical annotations**
- Fill in Gene Name and Clinical Significance fields
- Add HGVS annotations if available

## Contributing

To modify or extend the tool:

1. Edit the HTML file directly
2. Test changes in multiple browsers
3. Validate generated VCF files with standard tools
4. Update documentation as needed

## License

This tool is provided for educational and research purposes. Users are responsible for ensuring appropriate use in their specific context.

## References

- [VCF Format Specification v4.3](https://samtools.github.io/hts-specs/VCFv4.3.pdf)
- [HGVS Nomenclature Guidelines](https://hgvs-nomenclature.org/)
- [ClinVar Database](https://www.ncbi.nlm.nih.gov/clinvar/)
- [dbSNP Database](https://www.ncbi.nlm.nih.gov/snp/)
